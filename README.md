`sbt compile` results in compiler crash with following stack trace (Java 17 on MacOS) 

Uncommenting the `akka-stream` dependency prevents the crash. 

Note: adding `akka-stream` dep is required because it is just a [Provided dep](https://doc.akka.io/docs/akka-http/current/introduction.html#using-akka-http) in `akka-http`

Here is my stack trace:

<details>
  <summary>Click me</summary>

  ```txt
~/p/s/akka-http-compiler-crash (main) sbt compile
[info] welcome to sbt 1.8.0 (Eclipse Adoptium Java 17.0.2)
[info] loading global plugins from /Users/mushtaqahmed/.sbt/1.0/plugins
[info] loading settings for project akka-http-compiler-crash-build from plugins.sbt ...
[info] loading project definition from /Users/mushtaqahmed/projects/scala3/akka-http-compiler-crash/project
[info] loading settings for project root from build.sbt ...
[info] set current project to akka-http-compiler-crash (in build file:/Users/mushtaqahmed/projects/scala3/akka-http-compiler-crash/)
[info] Executing in batch mode. For better performance use sbt's shell
[info] compiling 1 Scala source to /Users/mushtaqahmed/projects/scala3/akka-http-compiler-crash/target/scala-3.2.1/classes ...
Error while emitting Demo.scala
java.lang.AssertionError: assertion failed while running genBCode on /Users/mushtaqahmed/projects/scala3/akka-http-compiler-crash/src/main/scala/com/example/Demo.scala
[info] exception occurred while compiling /Users/mushtaqahmed/projects/scala3/akka-http-compiler-crash/src/main/scala/com/example/Demo.scala
java.lang.AssertionError: assertion failed while compiling /Users/mushtaqahmed/projects/scala3/akka-http-compiler-crash/src/main/scala/com/example/Demo.scala
[error] ## Exception when compiling 1 sources to /Users/mushtaqahmed/projects/scala3/akka-http-compiler-crash/target/scala-3.2.1/classes
[error] java.lang.AssertionError: assertion failed
[error] scala.runtime.Scala3RunTime$.assertFailed(Scala3RunTime.scala:11)
[error] dotty.tools.dotc.core.Types$MethodType.<init>(Types.scala:3874)
[error] dotty.tools.dotc.core.Types$CachedMethodType.<init>(Types.scala:3894)
[error] dotty.tools.dotc.core.Types$MethodTypeCompanion.apply(Types.scala:3965)
[error] dotty.tools.dotc.core.Types$MethodTypeCompanion.apply(Types.scala:3964)
[error] dotty.tools.dotc.core.Types$LambdaTypeCompanion.apply(Types.scala:3906)
[error] dotty.tools.dotc.core.TypeErasure.eraseInfo(TypeErasure.scala:740)
[error] dotty.tools.dotc.core.TypeErasure$.transformInfo(TypeErasure.scala:244)
[error] dotty.tools.dotc.transform.Erasure.transform(Erasure.scala:97)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:833)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Symbols$Symbol.recomputeDenot(Symbols.scala:120)
[error] dotty.tools.dotc.core.Symbols$Symbol.computeDenot(Symbols.scala:114)
[error] dotty.tools.dotc.core.Symbols$Symbol.denot(Symbols.scala:107)
[error] dotty.tools.dotc.core.Symbols$.toDenot(Symbols.scala:497)
[error] dotty.tools.dotc.transform.Mixin.needsTraitSetter(Mixin.scala:174)
[error] dotty.tools.dotc.transform.Mixin.transformSym$$anonfun$1(Mixin.scala:153)
[error] scala.runtime.function.JProcedure1.apply(JProcedure1.java:15)
[error] scala.runtime.function.JProcedure1.apply(JProcedure1.java:10)
[error] scala.collection.immutable.List.foreach(List.scala:333)
[error] dotty.tools.dotc.core.Scopes$Scope.foreach(Scopes.scala:93)
[error] dotty.tools.dotc.transform.Mixin.transformSym(Mixin.scala:157)
[error] dotty.tools.dotc.core.DenotTransformers$SymTransformer.transform(DenotTransformers.scala:70)
[error] dotty.tools.dotc.core.DenotTransformers$SymTransformer.transform$(DenotTransformers.scala:65)
[error] dotty.tools.dotc.transform.Mixin.transform(Mixin.scala:113)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:833)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] dotty.tools.dotc.core.Symbols$Symbol.recomputeDenot(Symbols.scala:120)
[error] dotty.tools.dotc.core.Symbols$Symbol.computeDenot(Symbols.scala:114)
[error] dotty.tools.dotc.core.Symbols$Symbol.denot(Symbols.scala:107)
[error] dotty.tools.dotc.core.Symbols$.toDenot(Symbols.scala:497)
[error] dotty.tools.dotc.core.SymDenotations$ClassDenotation.registeredCompanion(SymDenotations.scala:2328)
[error] dotty.tools.dotc.core.SymDenotations$SymDenotation.companionType(SymDenotations.scala:1220)
[error] dotty.tools.dotc.core.SymDenotations$SymDenotation.companionClass(SymDenotations.scala:1228)
[error] dotty.tools.dotc.core.SymDenotations$SymDenotation.linkedClass(SymDenotations.scala:1270)
[error] dotty.tools.backend.jvm.BTypesFromSymbols.setClassInfo(BTypesFromSymbols.scala:175)
[error] dotty.tools.backend.jvm.BTypesFromSymbols.classBTypeFromSymbol$$anonfun$1(BTypesFromSymbols.scala:91)
[error] scala.collection.mutable.HashMap.getOrElse(HashMap.scala:436)
[error] dotty.tools.backend.jvm.BTypesFromSymbols.classBTypeFromSymbol(BTypesFromSymbols.scala:92)
[error] dotty.tools.backend.jvm.BCodeHelpers$BCInnerClassGen.getClassBType(BCodeHelpers.scala:261)
[error] dotty.tools.backend.jvm.BCodeHelpers$BCInnerClassGen.getClassBType$(BCodeHelpers.scala:213)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.getClassBType(BCodeSkelBuilder.scala:74)
[error] dotty.tools.backend.jvm.BCodeHelpers.primitiveOrClassToBType$1$$anonfun$1(BCodeHelpers.scala:798)
[error] scala.collection.immutable.HashMap.getOrElse(HashMap.scala:683)
[error] dotty.tools.backend.jvm.BCodeHelpers.primitiveOrClassToBType$1(BCodeHelpers.scala:798)
[error] dotty.tools.backend.jvm.BCodeHelpers.dotty$tools$backend$jvm$BCodeHelpers$$typeToTypeKind(BCodeHelpers.scala:817)
[error] dotty.tools.backend.jvm.BCodeHelpers$BCInnerClassGen.toTypeKind(BCodeHelpers.scala:285)
[error] dotty.tools.backend.jvm.BCodeHelpers$BCInnerClassGen.toTypeKind$(BCodeHelpers.scala:213)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.toTypeKind(BCodeSkelBuilder.scala:74)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.symInfoTK(BCodeSkelBuilder.scala:103)
[error] dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoadTo(BCodeBodyBuilder.scala:395)
[error] dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoad(BCodeBodyBuilder.scala:290)
[error] dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoadArguments(BCodeBodyBuilder.scala:1166)
[error] dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genApply(BCodeBodyBuilder.scala:802)
[error] dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoadTo(BCodeBodyBuilder.scala:369)
[error] dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoadTo(BCodeBodyBuilder.scala:439)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.emitNormalMethodBody$1(BCodeSkelBuilder.scala:809)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.genDefDef(BCodeSkelBuilder.scala:832)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.gen(BCodeSkelBuilder.scala:615)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.gen$$anonfun$1(BCodeSkelBuilder.scala:621)
[error] scala.runtime.function.JProcedure1.apply(JProcedure1.java:15)
[error] scala.runtime.function.JProcedure1.apply(JProcedure1.java:10)
[error] scala.collection.immutable.List.foreach(List.scala:333)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.gen(BCodeSkelBuilder.scala:621)
[error] dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.genPlainClass(BCodeSkelBuilder.scala:233)
[error] dotty.tools.backend.jvm.GenBCodePipeline$Worker1.visit(GenBCode.scala:266)
[error] dotty.tools.backend.jvm.GenBCodePipeline$Worker1.run(GenBCode.scala:231)
[error] dotty.tools.backend.jvm.GenBCodePipeline.buildAndSendToDisk(GenBCode.scala:598)
[error] dotty.tools.backend.jvm.GenBCodePipeline.run(GenBCode.scala:564)
[error] dotty.tools.backend.jvm.GenBCode.run(GenBCode.scala:69)
[error] dotty.tools.dotc.core.Phases$Phase.runOn$$anonfun$1(Phases.scala:316)
[error] scala.collection.immutable.List.map(List.scala:246)
[error] dotty.tools.dotc.core.Phases$Phase.runOn(Phases.scala:320)
[error] dotty.tools.backend.jvm.GenBCode.runOn(GenBCode.scala:77)
[error] dotty.tools.dotc.Run.runPhases$1$$anonfun$1(Run.scala:233)
[error] scala.runtime.function.JProcedure1.apply(JProcedure1.java:15)
[error] scala.runtime.function.JProcedure1.apply(JProcedure1.java:10)
[error] scala.collection.ArrayOps$.foreach$extension(ArrayOps.scala:1321)
[error] dotty.tools.dotc.Run.runPhases$1(Run.scala:244)
[error] dotty.tools.dotc.Run.compileUnits$$anonfun$1(Run.scala:252)
[error] dotty.tools.dotc.Run.compileUnits$$anonfun$adapted$1(Run.scala:261)
[error] dotty.tools.dotc.util.Stats$.maybeMonitored(Stats.scala:68)
[error] dotty.tools.dotc.Run.compileUnits(Run.scala:261)
[error] dotty.tools.dotc.Run.compileSources(Run.scala:185)
[error] dotty.tools.dotc.Run.compile(Run.scala:169)
[error] dotty.tools.dotc.Driver.doCompile(Driver.scala:35)
[error] dotty.tools.xsbt.CompilerBridgeDriver.run(CompilerBridgeDriver.java:88)
[error] dotty.tools.xsbt.CompilerBridge.run(CompilerBridge.java:22)
[error] sbt.internal.inc.AnalyzingCompiler.compile(AnalyzingCompiler.scala:91)
[error] sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$7(MixedAnalyzingCompiler.scala:193)
[error] scala.runtime.java8.JFunction0$mcV$sp.apply(JFunction0$mcV$sp.java:23)
[error] sbt.internal.inc.MixedAnalyzingCompiler.timed(MixedAnalyzingCompiler.scala:248)
[error] sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$4(MixedAnalyzingCompiler.scala:183)
[error] sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$4$adapted(MixedAnalyzingCompiler.scala:163)
[error] sbt.internal.inc.JarUtils$.withPreviousJar(JarUtils.scala:239)
[error] sbt.internal.inc.MixedAnalyzingCompiler.compileScala$1(MixedAnalyzingCompiler.scala:163)
[error] sbt.internal.inc.MixedAnalyzingCompiler.compile(MixedAnalyzingCompiler.scala:211)
[error] sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileInternal$1(IncrementalCompilerImpl.scala:534)
[error] sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileInternal$1$adapted(IncrementalCompilerImpl.scala:534)
[error] sbt.internal.inc.Incremental$.$anonfun$apply$5(Incremental.scala:179)
[error] sbt.internal.inc.Incremental$.$anonfun$apply$5$adapted(Incremental.scala:177)
[error] sbt.internal.inc.Incremental$$anon$2.run(Incremental.scala:463)
[error] sbt.internal.inc.IncrementalCommon$CycleState.next(IncrementalCommon.scala:116)
[error] sbt.internal.inc.IncrementalCommon$$anon$1.next(IncrementalCommon.scala:56)
[error] sbt.internal.inc.IncrementalCommon$$anon$1.next(IncrementalCommon.scala:52)
[error] sbt.internal.inc.IncrementalCommon.cycle(IncrementalCommon.scala:263)
[error] sbt.internal.inc.Incremental$.$anonfun$incrementalCompile$8(Incremental.scala:418)
[error] sbt.internal.inc.Incremental$.withClassfileManager(Incremental.scala:506)
[error] sbt.internal.inc.Incremental$.incrementalCompile(Incremental.scala:405)
[error] sbt.internal.inc.Incremental$.apply(Incremental.scala:171)
[error] sbt.internal.inc.IncrementalCompilerImpl.compileInternal(IncrementalCompilerImpl.scala:534)
[error] sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileIncrementally$1(IncrementalCompilerImpl.scala:488)
[error] sbt.internal.inc.IncrementalCompilerImpl.handleCompilationError(IncrementalCompilerImpl.scala:332)
[error] sbt.internal.inc.IncrementalCompilerImpl.compileIncrementally(IncrementalCompilerImpl.scala:425)
[error] sbt.internal.inc.IncrementalCompilerImpl.compile(IncrementalCompilerImpl.scala:137)
[error] sbt.Defaults$.compileIncrementalTaskImpl(Defaults.scala:2363)
[error] sbt.Defaults$.$anonfun$compileIncrementalTask$2(Defaults.scala:2313)
[error] sbt.internal.server.BspCompileTask$.$anonfun$compute$1(BspCompileTask.scala:30)
[error] sbt.internal.io.Retry$.apply(Retry.scala:46)
[error] sbt.internal.io.Retry$.apply(Retry.scala:28)
[error] sbt.internal.io.Retry$.apply(Retry.scala:23)
[error] sbt.internal.server.BspCompileTask$.compute(BspCompileTask.scala:30)
[error] sbt.Defaults$.$anonfun$compileIncrementalTask$1(Defaults.scala:2311)
[error] scala.Function1.$anonfun$compose$1(Function1.scala:49)
[error] sbt.internal.util.$tilde$greater.$anonfun$$u2219$1(TypeFunctions.scala:62)
[error] sbt.std.Transform$$anon$4.work(Transform.scala:68)
[error] sbt.Execute.$anonfun$submit$2(Execute.scala:282)
[error] sbt.internal.util.ErrorHandling$.wideConvert(ErrorHandling.scala:23)
[error] sbt.Execute.work(Execute.scala:291)
[error] sbt.Execute.$anonfun$submit$1(Execute.scala:282)
[error] sbt.ConcurrentRestrictions$$anon$4.$anonfun$submitValid$1(ConcurrentRestrictions.scala:265)
[error] sbt.CompletionService$$anon$2.call(CompletionService.scala:64)
[error] java.base/java.util.concurrent.FutureTask.run(FutureTask.java:264)
[error] java.base/java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:539)
[error] java.base/java.util.concurrent.FutureTask.run(FutureTask.java:264)
[error] java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1136)
[error] java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:635)
[error] java.base/java.lang.Thread.run(Thread.java:833)
[error]
[error] java.lang.AssertionError: assertion failed
[error] 	at scala.runtime.Scala3RunTime$.assertFailed(Scala3RunTime.scala:11)
[error] 	at dotty.tools.dotc.core.Types$MethodType.<init>(Types.scala:3874)
[error] 	at dotty.tools.dotc.core.Types$CachedMethodType.<init>(Types.scala:3894)
[error] 	at dotty.tools.dotc.core.Types$MethodTypeCompanion.apply(Types.scala:3965)
[error] 	at dotty.tools.dotc.core.Types$MethodTypeCompanion.apply(Types.scala:3964)
[error] 	at dotty.tools.dotc.core.Types$LambdaTypeCompanion.apply(Types.scala:3906)
[error] 	at dotty.tools.dotc.core.TypeErasure.eraseInfo(TypeErasure.scala:740)
[error] 	at dotty.tools.dotc.core.TypeErasure$.transformInfo(TypeErasure.scala:244)
[error] 	at dotty.tools.dotc.transform.Erasure.transform(Erasure.scala:97)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:833)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Symbols$Symbol.recomputeDenot(Symbols.scala:120)
[error] 	at dotty.tools.dotc.core.Symbols$Symbol.computeDenot(Symbols.scala:114)
[error] 	at dotty.tools.dotc.core.Symbols$Symbol.denot(Symbols.scala:107)
[error] 	at dotty.tools.dotc.core.Symbols$.toDenot(Symbols.scala:497)
[error] 	at dotty.tools.dotc.transform.Mixin.needsTraitSetter(Mixin.scala:174)
[error] 	at dotty.tools.dotc.transform.Mixin.transformSym$$anonfun$1(Mixin.scala:153)
[error] 	at scala.runtime.function.JProcedure1.apply(JProcedure1.java:15)
[error] 	at scala.runtime.function.JProcedure1.apply(JProcedure1.java:10)
[error] 	at scala.collection.immutable.List.foreach(List.scala:333)
[error] 	at dotty.tools.dotc.core.Scopes$Scope.foreach(Scopes.scala:93)
[error] 	at dotty.tools.dotc.transform.Mixin.transformSym(Mixin.scala:157)
[error] 	at dotty.tools.dotc.core.DenotTransformers$SymTransformer.transform(DenotTransformers.scala:70)
[error] 	at dotty.tools.dotc.core.DenotTransformers$SymTransformer.transform$(DenotTransformers.scala:65)
[error] 	at dotty.tools.dotc.transform.Mixin.transform(Mixin.scala:113)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:833)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.goForward$1(Denotations.scala:853)
[error] 	at dotty.tools.dotc.core.Denotations$SingleDenotation.current(Denotations.scala:882)
[error] 	at dotty.tools.dotc.core.Symbols$Symbol.recomputeDenot(Symbols.scala:120)
[error] 	at dotty.tools.dotc.core.Symbols$Symbol.computeDenot(Symbols.scala:114)
[error] 	at dotty.tools.dotc.core.Symbols$Symbol.denot(Symbols.scala:107)
[error] 	at dotty.tools.dotc.core.Symbols$.toDenot(Symbols.scala:497)
[error] 	at dotty.tools.dotc.core.SymDenotations$ClassDenotation.registeredCompanion(SymDenotations.scala:2328)
[error] 	at dotty.tools.dotc.core.SymDenotations$SymDenotation.companionType(SymDenotations.scala:1220)
[error] 	at dotty.tools.dotc.core.SymDenotations$SymDenotation.companionClass(SymDenotations.scala:1228)
[error] 	at dotty.tools.dotc.core.SymDenotations$SymDenotation.linkedClass(SymDenotations.scala:1270)
[error] 	at dotty.tools.backend.jvm.BTypesFromSymbols.setClassInfo(BTypesFromSymbols.scala:175)
[error] 	at dotty.tools.backend.jvm.BTypesFromSymbols.classBTypeFromSymbol$$anonfun$1(BTypesFromSymbols.scala:91)
[error] 	at scala.collection.mutable.HashMap.getOrElse(HashMap.scala:436)
[error] 	at dotty.tools.backend.jvm.BTypesFromSymbols.classBTypeFromSymbol(BTypesFromSymbols.scala:92)
[error] 	at dotty.tools.backend.jvm.BCodeHelpers$BCInnerClassGen.getClassBType(BCodeHelpers.scala:261)
[error] 	at dotty.tools.backend.jvm.BCodeHelpers$BCInnerClassGen.getClassBType$(BCodeHelpers.scala:213)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.getClassBType(BCodeSkelBuilder.scala:74)
[error] 	at dotty.tools.backend.jvm.BCodeHelpers.primitiveOrClassToBType$1$$anonfun$1(BCodeHelpers.scala:798)
[error] 	at scala.collection.immutable.HashMap.getOrElse(HashMap.scala:683)
[error] 	at dotty.tools.backend.jvm.BCodeHelpers.primitiveOrClassToBType$1(BCodeHelpers.scala:798)
[error] 	at dotty.tools.backend.jvm.BCodeHelpers.dotty$tools$backend$jvm$BCodeHelpers$$typeToTypeKind(BCodeHelpers.scala:817)
[error] 	at dotty.tools.backend.jvm.BCodeHelpers$BCInnerClassGen.toTypeKind(BCodeHelpers.scala:285)
[error] 	at dotty.tools.backend.jvm.BCodeHelpers$BCInnerClassGen.toTypeKind$(BCodeHelpers.scala:213)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.toTypeKind(BCodeSkelBuilder.scala:74)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.symInfoTK(BCodeSkelBuilder.scala:103)
[error] 	at dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoadTo(BCodeBodyBuilder.scala:395)
[error] 	at dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoad(BCodeBodyBuilder.scala:290)
[error] 	at dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoadArguments(BCodeBodyBuilder.scala:1166)
[error] 	at dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genApply(BCodeBodyBuilder.scala:802)
[error] 	at dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoadTo(BCodeBodyBuilder.scala:369)
[error] 	at dotty.tools.backend.jvm.BCodeBodyBuilder$PlainBodyBuilder.genLoadTo(BCodeBodyBuilder.scala:439)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.emitNormalMethodBody$1(BCodeSkelBuilder.scala:809)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.genDefDef(BCodeSkelBuilder.scala:832)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.gen(BCodeSkelBuilder.scala:615)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.gen$$anonfun$1(BCodeSkelBuilder.scala:621)
[error] 	at scala.runtime.function.JProcedure1.apply(JProcedure1.java:15)
[error] 	at scala.runtime.function.JProcedure1.apply(JProcedure1.java:10)
[error] 	at scala.collection.immutable.List.foreach(List.scala:333)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.gen(BCodeSkelBuilder.scala:621)
[error] 	at dotty.tools.backend.jvm.BCodeSkelBuilder$PlainSkelBuilder.genPlainClass(BCodeSkelBuilder.scala:233)
[error] 	at dotty.tools.backend.jvm.GenBCodePipeline$Worker1.visit(GenBCode.scala:266)
[error] 	at dotty.tools.backend.jvm.GenBCodePipeline$Worker1.run(GenBCode.scala:231)
[error] 	at dotty.tools.backend.jvm.GenBCodePipeline.buildAndSendToDisk(GenBCode.scala:598)
[error] 	at dotty.tools.backend.jvm.GenBCodePipeline.run(GenBCode.scala:564)
[error] 	at dotty.tools.backend.jvm.GenBCode.run(GenBCode.scala:69)
[error] 	at dotty.tools.dotc.core.Phases$Phase.runOn$$anonfun$1(Phases.scala:316)
[error] 	at scala.collection.immutable.List.map(List.scala:246)
[error] 	at dotty.tools.dotc.core.Phases$Phase.runOn(Phases.scala:320)
[error] 	at dotty.tools.backend.jvm.GenBCode.runOn(GenBCode.scala:77)
[error] 	at dotty.tools.dotc.Run.runPhases$1$$anonfun$1(Run.scala:233)
[error] 	at scala.runtime.function.JProcedure1.apply(JProcedure1.java:15)
[error] 	at scala.runtime.function.JProcedure1.apply(JProcedure1.java:10)
[error] 	at scala.collection.ArrayOps$.foreach$extension(ArrayOps.scala:1321)
[error] 	at dotty.tools.dotc.Run.runPhases$1(Run.scala:244)
[error] 	at dotty.tools.dotc.Run.compileUnits$$anonfun$1(Run.scala:252)
[error] 	at dotty.tools.dotc.Run.compileUnits$$anonfun$adapted$1(Run.scala:261)
[error] 	at dotty.tools.dotc.util.Stats$.maybeMonitored(Stats.scala:68)
[error] 	at dotty.tools.dotc.Run.compileUnits(Run.scala:261)
[error] 	at dotty.tools.dotc.Run.compileSources(Run.scala:185)
[error] 	at dotty.tools.dotc.Run.compile(Run.scala:169)
[error] 	at dotty.tools.dotc.Driver.doCompile(Driver.scala:35)
[error] 	at dotty.tools.xsbt.CompilerBridgeDriver.run(CompilerBridgeDriver.java:88)
[error] 	at dotty.tools.xsbt.CompilerBridge.run(CompilerBridge.java:22)
[error] 	at sbt.internal.inc.AnalyzingCompiler.compile(AnalyzingCompiler.scala:91)
[error] 	at sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$7(MixedAnalyzingCompiler.scala:193)
[error] 	at scala.runtime.java8.JFunction0$mcV$sp.apply(JFunction0$mcV$sp.java:23)
[error] 	at sbt.internal.inc.MixedAnalyzingCompiler.timed(MixedAnalyzingCompiler.scala:248)
[error] 	at sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$4(MixedAnalyzingCompiler.scala:183)
[error] 	at sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$4$adapted(MixedAnalyzingCompiler.scala:163)
[error] 	at sbt.internal.inc.JarUtils$.withPreviousJar(JarUtils.scala:239)
[error] 	at sbt.internal.inc.MixedAnalyzingCompiler.compileScala$1(MixedAnalyzingCompiler.scala:163)
[error] 	at sbt.internal.inc.MixedAnalyzingCompiler.compile(MixedAnalyzingCompiler.scala:211)
[error] 	at sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileInternal$1(IncrementalCompilerImpl.scala:534)
[error] 	at sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileInternal$1$adapted(IncrementalCompilerImpl.scala:534)
[error] 	at sbt.internal.inc.Incremental$.$anonfun$apply$5(Incremental.scala:179)
[error] 	at sbt.internal.inc.Incremental$.$anonfun$apply$5$adapted(Incremental.scala:177)
[error] 	at sbt.internal.inc.Incremental$$anon$2.run(Incremental.scala:463)
[error] 	at sbt.internal.inc.IncrementalCommon$CycleState.next(IncrementalCommon.scala:116)
[error] 	at sbt.internal.inc.IncrementalCommon$$anon$1.next(IncrementalCommon.scala:56)
[error] 	at sbt.internal.inc.IncrementalCommon$$anon$1.next(IncrementalCommon.scala:52)
[error] 	at sbt.internal.inc.IncrementalCommon.cycle(IncrementalCommon.scala:263)
[error] 	at sbt.internal.inc.Incremental$.$anonfun$incrementalCompile$8(Incremental.scala:418)
[error] 	at sbt.internal.inc.Incremental$.withClassfileManager(Incremental.scala:506)
[error] 	at sbt.internal.inc.Incremental$.incrementalCompile(Incremental.scala:405)
[error] 	at sbt.internal.inc.Incremental$.apply(Incremental.scala:171)
[error] 	at sbt.internal.inc.IncrementalCompilerImpl.compileInternal(IncrementalCompilerImpl.scala:534)
[error] 	at sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileIncrementally$1(IncrementalCompilerImpl.scala:488)
[error] 	at sbt.internal.inc.IncrementalCompilerImpl.handleCompilationError(IncrementalCompilerImpl.scala:332)
[error] 	at sbt.internal.inc.IncrementalCompilerImpl.compileIncrementally(IncrementalCompilerImpl.scala:425)
[error] 	at sbt.internal.inc.IncrementalCompilerImpl.compile(IncrementalCompilerImpl.scala:137)
[error] 	at sbt.Defaults$.compileIncrementalTaskImpl(Defaults.scala:2363)
[error] 	at sbt.Defaults$.$anonfun$compileIncrementalTask$2(Defaults.scala:2313)
[error] 	at sbt.internal.server.BspCompileTask$.$anonfun$compute$1(BspCompileTask.scala:30)
[error] 	at sbt.internal.io.Retry$.apply(Retry.scala:46)
[error] 	at sbt.internal.io.Retry$.apply(Retry.scala:28)
[error] 	at sbt.internal.io.Retry$.apply(Retry.scala:23)
[error] 	at sbt.internal.server.BspCompileTask$.compute(BspCompileTask.scala:30)
[error] 	at sbt.Defaults$.$anonfun$compileIncrementalTask$1(Defaults.scala:2311)
[error] 	at scala.Function1.$anonfun$compose$1(Function1.scala:49)
[error] 	at sbt.internal.util.$tilde$greater.$anonfun$$u2219$1(TypeFunctions.scala:62)
[error] 	at sbt.std.Transform$$anon$4.work(Transform.scala:68)
[error] 	at sbt.Execute.$anonfun$submit$2(Execute.scala:282)
[error] 	at sbt.internal.util.ErrorHandling$.wideConvert(ErrorHandling.scala:23)
[error] 	at sbt.Execute.work(Execute.scala:291)
[error] 	at sbt.Execute.$anonfun$submit$1(Execute.scala:282)
[error] 	at sbt.ConcurrentRestrictions$$anon$4.$anonfun$submitValid$1(ConcurrentRestrictions.scala:265)
[error] 	at sbt.CompletionService$$anon$2.call(CompletionService.scala:64)
[error] 	at java.base/java.util.concurrent.FutureTask.run(FutureTask.java:264)
[error] 	at java.base/java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:539)
[error] 	at java.base/java.util.concurrent.FutureTask.run(FutureTask.java:264)
[error] 	at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1136)
[error] 	at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:635)
[error] 	at java.base/java.lang.Thread.run(Thread.java:833)
[error] (Compile / compileIncremental) java.lang.AssertionError: assertion failed
[error] Total time: 2 s, completed 17 Nov 2022, 22:23:23
~/p/s/akka-http-compiler-crash (main)
  ```
</details>