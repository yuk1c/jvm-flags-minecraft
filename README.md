## 🚀 JVM Flags to Boost Minecraft FPS.

### 📋 Requirements
- Latest Java (i tested only JDK 20.0.1)
- Latest Minecraft (i tested only 1.20.1)

### 🧩 JVM Flags
```
-XX:+UnlockExperimentalVMOptions -XX:+UseG1GC -XX:G1NewSizePercent=20 -XX:G1ReservePercent=20 -XX:MaxGCPauseMillis=50 -XX:G1HeapRegionSize=32M -Dfml.ignoreInvalidMinecraftCertificates=true -Dfml.ignorePatchDiscrepancies=true -Djava.net.preferIPv4Stack=true -XX:+AlwaysActAsServerClassMachine -XX:+DisableExplicitGC -XX:NmethodSweepActivity=1 -XX:-DontCompileHugeMethods -XX:MaxNodeLimit=640000 -XX:NodeLimitFudgeFactor=30000 -XX:+UseVectorCmov -XX:+PerfDisableSharedMem -XX:+UseFastUnorderedTimeStamps -XX:+UseCriticalJavaThreadPriority -XX:ThreadPriorityPolicy=1 -XX:AllocatePrefetchStyle=3 -XX:+UseLargePages -XX:+UseStringDeduplication -XX:+UseCompressedOops -XX:+OptimizeStringConcat
```

### 🎓 Flag description
-XX:+UseG1GC: This option enables the Garbage-First (G1) garbage collector, which is designed to provide better garbage collection performance with low pause times.

-XX:G1NewSizePercent=20: This option sets the percentage of the heap to be used as the size of the young generation for the G1 collector. In this case, it sets the young generation size to 20% of the heap.

-XX:G1ReservePercent=20: This option reserves a percentage of the heap as a safeguard against potential fragmentation. It ensures that a certain portion of the heap is available for allocation during the G1 garbage collection.

-XX:MaxGCPauseMillis=50: This option sets the target maximum pause time for garbage collection in milliseconds. The G1 collector will try to meet this goal by dynamically adjusting various parameters.

-XX:G1HeapRegionSize=32M: This option sets the size of the G1 heap regions. The heap is divided into regions, and this parameter defines the size of each region. In this case, each region will have a size of 32 megabytes.

-Dfml.ignoreInvalidMinecraftCertificates=true: This option is a system property for Forge Mod Loader (FML) in Minecraft. It allows the game to ignore invalid certificates, which can be useful when dealing with custom or unofficial mods.

-Dfml.ignorePatchDiscrepancies=true: Another system property for FML in Minecraft, this option allows the game to ignore discrepancies between applied patches. It can help in situations where mods have conflicting changes.

-Djava.net.preferIPv4Stack=true: This option tells Java to prefer the IPv4 stack when resolving network addresses. It can be useful if there are issues with IPv6 connectivity or compatibility.

-XX:+AlwaysActAsServerClassMachine: This option instructs the JVM to always act as if it is running on a server-class machine, enabling optimizations specific to server environments.

-XX:+DisableExplicitGC: This option disables explicit garbage collection calls (System.gc()). Explicit garbage collection is generally discouraged, as the JVM performs garbage collection automatically.

-XX:NmethodSweepActivity=1: This option controls the aggressiveness of the nmethod sweeping activity in the JVM. It affects the frequency and intensity of sweeping unused compiled code.

-XX:-DontCompileHugeMethods: By default, the JVM may avoid compiling very large methods. This option disables that behavior and allows huge methods to be compiled.

-XX:MaxNodeLimit=640000: This option sets the maximum number of nodes that can be created during compilation. It helps limit memory usage during the compilation process.

-XX:NodeLimitFudgeFactor=30000: This option sets a fudge factor that allows for some additional node creation beyond the maximum limit defined by MaxNodeLimit. It provides flexibility while staying within the defined limit.

-XX:+UseVectorCmov: This option enables the usage of vectorized compare and move (cmov) instructions for better performance on CPUs that support these instructions.

-XX:+PerfDisableSharedMem: This option disables the use of shared memory for JVM performance counters. It can be useful in certain environments where shared memory is not available or not desired.

-XX:+UseFastUnorderedTimeStamps: This option enables the usage of fast unordered timestamps for time-related operations in the JVM.

-XX:+UseCriticalJavaThreadPriority: This option assigns a higher priority to critical Java threads, which can improve responsiveness and reduce latency in critical parts of the application.

-XX:ThreadPriorityPolicy=1: This option sets the thread priority policy for the JVM. In this case, it sets the policy to use the operating system's thread priority mechanism.

-XX:AllocatePrefetchStyle=3: This option controls the style of prefetching used for object allocation in the JVM. A value of 3 enables the most aggressive prefetching.

-XX:+UseLargePages: This option enables the usage of large pages for the JVM's memory allocation. Large pages can improve performance by reducing TLB (Translation Lookaside Buffer) misses.

-XX:+UseStringDeduplication: This option enables the deduplication of identical strings in the JVM's string pool. It helps reduce memory usage when multiple instances of the same string are present.

-XX:+UseCompressedOops: This option enables the use of compressed object pointers in the JVM, which reduces memory usage on 64-bit systems.

-XX:+OptimizeStringConcat: This option enables optimized string concatenation in the JVM, which can lead to improved performance when working with string concatenation operations.
