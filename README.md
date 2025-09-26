## Current Project
A zig ECS that resembles bevy_ecs.

Not ready for release yet.

Systems are pretty much done making this a true Entity-Component-**System**

```zig
const std = @import("std");
const ecs = @import("ecs");

// Define your event types
const GameEvent = union(enum) {
    player_died: struct { player_id: u32 },
    enemy_spawned: struct { enemy_type: []const u8, x: f32, y: f32 },
    level_complete: void,
};

const InputEvent = union(enum) {
    key_pressed: struct { key: u8 },
    mouse_clicked: struct { x: f32, y: f32 },
};

// Example system that reads game events
fn game_event_reader(_: *ecs.Manager, game_events: *ecs.EventReader(GameEvent)) void {
    std.debug.print("Game Event Reader - Processing {d} events\n", .{game_events.len()});

    while (game_events.read()) |e| {
        switch (e.data) {
            .player_died => |data| {
                std.debug.print("Player {d} died!\n", .{data.player_id});
                e.handled = true; // Mark as handled
            },
            .enemy_spawned => |data| {
                std.debug.print("Enemy {s} spawned at ({d}, {d})\n", .{ data.enemy_type, data.x, data.y });
                e.handled = true; // Mark as handled
            },
            .level_complete => {
                std.debug.print("Level complete!\n", .{});
                // Don't mark as handled - let another system handle this
            },
        }
    }
}

// Example system that writes input events
fn input_event_writer(_: *ecs.Manager, writer: *ecs.EventWriter(InputEvent)) void {
    std.debug.print("Input Event Writer - Adding events\n", .{});

    // Simulate some input events
    writer.write(.{ .key_pressed = .{ .key = 'A' } });
    writer.write(.{ .mouse_clicked = .{ .x = 100.0, .y = 200.0 } });
}

pub fn main() !void {
    const allocator = std.heap.page_allocator;
    // DefaultRegistyr is SystemParamRegistry, just a tuple of comptime types that use SystemParam interface.
    const DefaultSystemParamRegistry = ecs.DefaultRegistry;

    // Initialize ECS
    var ecs_instance = try ecs.Manager.init(allocator);
    defer ecs_instance.deinit();

    // Initialize Scheduler
    var scheduler = try ecs.Scheduler.init(allocator, &ecs_instance);
    defer scheduler.deinit();

    // Register event types with the scheduler
    // This automatically creates EventStore resources and cleanup systems
    try scheduler.registerEvent(&ecs_instance, GameEvent);
    try scheduler.registerEvent(&ecs_instance, InputEvent);

    // Create systems
    const game_reader_sys = ecs_instance.createSystemCached(game_event_reader, DefaultSystemParamRegistry);
    const input_writer_sys = ecs_instance.createSystemCached(input_event_writer, DefaultSystemParamRegistry);

    // Add systems to appropriate stages
    // Stages.Update.stage() returns a i16
    scheduler.addSystem(ecs.Stages.Update.stage(), game_reader_sys);
    scheduler.addSystem(ecs.Stages.Update.stage(), input_writer_sys);

    std.debug.print("=== Initial State ===\n", .{});

    std.debug.print("\n=== Update Stage ===\n", .{});
    try scheduler.runStage(&ecs_instance, ecs.Stages.Update.stage());

    std.debug.print("\n=== Last Stage (Cleanup) ===\n", .{});
    try scheduler.runStage(&ecs_instance, ecs.Stages.Last.stage());
}
```

Looks a lot like bevy doesn't it?  Besides the changes needed to make it work in the zig ecosystem.

Performance is amazing!
```
ManagerType 7 mixed queries 2,000,000
ops:       10    10.594 ms/op     0.000 B/op

ManagerType 7 mixed systems 2,000,000
ops:       10    15.330 ms/op   376.000 B/op
```

No I am not making a bevy clone.  Just having fun trying what's possible in zig.  It is a pretty impressive language and great for those that don't need the borrow checker to treat you like a kid.

<!--
**captkirk88/captkirk88** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
