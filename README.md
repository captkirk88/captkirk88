## Current Project
A zig ECS that resembles bevy_ecs.

Not ready for release yet.

Quite a lot of progress so far.
```
Benchmark Results:
ECS entity creation 100000
ops:       10    29.796 ms/op    26.890 MB/op
Benchmark Results:
ECS batch creation 100000
ops:       10    12.285 ms/op    23.838 MB/op
Entity count after: 100000
Benchmark Results:
ECS querying 100000
ops:      100   261.625 us/op     0.000 B/op
Entity count after system run: 100000
Benchmark Results:
ECS system multi Query/Res/Local 100000
ops:       10   515.220 us/op   112.000 B/op
Benchmark Results:
ECS add component 1
ops:       10   530.000 ns/op   102.000 B/op
Benchmark Results:
ECS add component 100000
ops:       10    31.150 ms/op     6.513 MB/op
Benchmark Results:
ECS remove component 1
ops:       10   390.000 ns/op    24.000 B/op
Benchmark Results:
ECS remove component 100000
ops:       10     1.820 ms/op   312.521 KB/op
Benchmark Results:
EventStore push 100
ops:       10     2.990 us/op     0.000 B/op
Benchmark Results:
EventStore iterate 100
ops:       10   600.000 ns/op     0.000 B/op
Benchmark Results:
EventStore clear 100
ops:       10     1.080 us/op     0.000 B/op
Benchmark Results:
EntityCommands batch add 1
ops:       10     3.080 us/op   588.000 B/op
Benchmark Results:
EntityCommands batch add 100000
ops:       10   188.613 ms/op    40.797 MB/op
Benchmark Results:
ECS 7 mixed queries 1
ops:       10   480.000 ns/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 4
ops:       10   450.000 ns/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 8
ops:       10   560.000 ns/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 16
ops:       10   480.000 ns/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 32
ops:       10   880.000 ns/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 64
ops:       10     1.120 us/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 256
ops:       10     2.190 us/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 1000
ops:       10     8.090 us/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 4000
ops:       10    20.550 us/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 16000
ops:       10    79.440 us/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 65000
ops:       10   321.210 us/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 262000
ops:       10     1.298 ms/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 1000000
ops:       10     5.094 ms/op     0.000 B/op
Benchmark Results:
ECS 7 mixed queries 2000000
ops:       10    10.331 ms/op     0.000 B/op
Benchmark Results:
ECS 7 mixed systems 1
ops:       10     1.000 us/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 4
ops:       10   890.000 ns/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 8
ops:       10   930.000 ns/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 16
ops:       10   960.000 ns/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 32
ops:       10     1.090 us/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 64
ops:       10     2.070 us/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 256
ops:       10     3.440 us/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 1000
ops:       10    12.560 us/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 4000
ops:       10    29.200 us/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 16000
ops:       10   113.710 us/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 65000
ops:       10   456.920 us/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 262000
ops:       10     1.913 ms/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 1000000
ops:       10     7.452 ms/op   376.000 B/op
Benchmark Results:
ECS 7 mixed systems 2000000
ops:       10    14.839 ms/op   376.000 B/op
```

Also features systems, yes, like how bevy does it.

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
