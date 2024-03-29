# Traveler Process
## KIE Sandbox Sample
### Result: Fails to build?

#### Create project from Sandbox
1. Open [KIE Sandbox](sandbox.kie.org/)
2. Click [Try Sample](https://sandbox.kie.org/#/import?url=https://sandbox.kie.org/samples/Sample.bpmn) under "Workflow"
3. Click "Apply Accelerator" > "Quarkus..." > Accept
4. Click "Share" > (Download) "All files"

#### Build local project (JVM)
1. Compile to run with JVM
      ``` log
      mvn clean package
      ```
2. Error messages
     ``` log
     [ERROR] Failed to execute goal io.quarkus:quarkus-maven-plugin:2.15.3.Final:build (default) on project quarkus-accelerator: Failed to build quarkus application: io.quarkus.builder.BuildException: Build failure: Build failed due to errors
      [ERROR] 	[error]: Build step org.kie.kogito.quarkus.common.deployment.KogitoAssetsProcessor#generateModel threw an exception: org.kie.memorycompiler.KieMemoryCompilerException: [org/kie/kogito/test/TravelersMessageProducer_7.java (24:88) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModel.java (42:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModel.java (44:27) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModel.java (48:45) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelOutput.java (42:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelOutput.java (44:27) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelOutput.java (48:45) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelInput.java (34:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelInput.java (36:27) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelInput.java (40:45) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (24:53) : package org.kie.kogito.addon.quarkus.messaging.common does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (28:49) : cannot find symbol
      [ERROR]   symbol: class QuarkusMessageConsumer, org/kie/kogito/test/TravelersMessageConsumer_3.java (28:103) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (44:56) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (53:48) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (62:112) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (73:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (73:67) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (87:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (87:67) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (147:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (147:67) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (151:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (151:67) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (168:102) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (41:52) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (52:5) : method does not override or implement a method from a supertype]
      [ERROR] 	at org.kie.memorycompiler.KieMemoryCompiler.compileNoLoad(KieMemoryCompiler.java:137)
      [ERROR] 	at org.kie.memorycompiler.KieMemoryCompiler.compileNoLoad(KieMemoryCompiler.java:105)
      [ERROR] 	at org.drools.drl.quarkus.util.deployment.DroolsQuarkusResourceUtils.compileGeneratedSources(DroolsQuarkusResourceUtils.java:153)
      [ERROR] 	at org.kie.kogito.quarkus.common.deployment.KogitoAssetsProcessor.createGeneratedBeanBuildItemsFromJavaSources(KogitoAssetsProcessor.java:273)
      [ERROR] 	at org.kie.kogito.quarkus.common.deployment.KogitoAssetsProcessor.generateModel(KogitoAssetsProcessor.java:182)
      [ERROR] 	at java.base/jdk.internal.reflect.DirectMethodHandleAccessor.invoke(DirectMethodHandleAccessor.java:103)
      [ERROR] 	at java.base/java.lang.reflect.Method.invoke(Method.java:580)
      [ERROR] 	at io.quarkus.deployment.ExtensionLoader$3.execute(ExtensionLoader.java:909)
      [ERROR] 	at io.quarkus.builder.BuildContext.run(BuildContext.java:281)
      [ERROR] 	at org.jboss.threads.ContextHandler$1.runWith(ContextHandler.java:18)
      [ERROR] 	at org.jboss.threads.EnhancedQueueExecutor$Task.run(EnhancedQueueExecutor.java:2449)
      [ERROR] 	at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.run(EnhancedQueueExecutor.java:1478)
      [ERROR] 	at java.base/java.lang.Thread.run(Thread.java:1583)
      [ERROR] 	at org.jboss.threads.JBossThread.run(JBossThread.java:501)
      [ERROR] -> [Help 1]
     ```

#### Build local project (Quarkus)
1. Compile to run with Quarkus
      ``` log
      mvn clean compile quarkus:dev
      ```
2. Error messages
     ``` log
           2024-03-26 16:24:09,845 ERROR [io.qua.dep.dev.IsolatedDevModeMain] (main) Failed to start quarkus: java.lang.RuntimeException: io.quarkus.builder.BuildException: Build failure: Build failed due to errors
            [error]: Build step org.kie.kogito.quarkus.common.deployment.KogitoAssetsProcessor#generateModel threw an exception: org.kie.memorycompiler.KieMemoryCompilerException: [org/kie/kogito/test/TravelersMessageProducer_7.java (24:88) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModel.java (42:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModel.java (44:27) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModel.java (48:45) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelOutput.java (42:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelOutput.java (44:27) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelOutput.java (48:45) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelInput.java (34:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelInput.java (36:27) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersModelInput.java (40:45) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (24:53) : package org.kie.kogito.addon.quarkus.messaging.common does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (28:49) : cannot find symbol
        symbol: class QuarkusMessageConsumer, org/kie/kogito/test/TravelersMessageConsumer_3.java (28:103) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (44:56) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (53:48) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (62:112) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (73:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (73:67) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (87:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (87:67) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (147:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (147:67) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (151:28) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (151:67) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersProcess.java (168:102) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (41:52) : package org.acme.travel does not exist, org/kie/kogito/test/TravelersMessageConsumer_3.java (52:5) : method does not override or implement a method from a supertype]
            at org.kie.memorycompiler.KieMemoryCompiler.compileNoLoad(KieMemoryCompiler.java:137)
            at org.kie.memorycompiler.KieMemoryCompiler.compileNoLoad(KieMemoryCompiler.java:105)
            at org.drools.drl.quarkus.util.deployment.DroolsQuarkusResourceUtils.compileGeneratedSources(DroolsQuarkusResourceUtils.java:153)
            at org.kie.kogito.quarkus.common.deployment.KogitoAssetsProcessor.createGeneratedBeanBuildItemsFromJavaSources(KogitoAssetsProcessor.java:273)
            at org.kie.kogito.quarkus.common.deployment.KogitoAssetsProcessor.generateModel(KogitoAssetsProcessor.java:182)
            at java.base/jdk.internal.reflect.DirectMethodHandleAccessor.invoke(DirectMethodHandleAccessor.java:103)
            at java.base/java.lang.reflect.Method.invoke(Method.java:580)
            at io.quarkus.deployment.ExtensionLoader$3.execute(ExtensionLoader.java:909)
            at io.quarkus.builder.BuildContext.run(BuildContext.java:281)
            at org.jboss.threads.ContextHandler$1.runWith(ContextHandler.java:18)
            at org.jboss.threads.EnhancedQueueExecutor$Task.run(EnhancedQueueExecutor.java:2449)
            at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.run(EnhancedQueueExecutor.java:1478)
            at java.base/java.lang.Thread.run(Thread.java:1583)
            at org.jboss.threads.JBossThread.run(JBossThread.java:501)

     ```
### No Kogito
Quarkus runs, kafka warnings
```
2024-03-29 11:18:14,549 INFO  [io.sma.rea.mes.kafka] (smallrye-kafka-producer-thread-0) SRMSG18258: Kafka producer kafka-producer-kogito-processinstances-events, connected to Kafka brokers 'localhost:9092', is configured to write records to 'kogito-processinstances-events'
2024-03-29 11:18:14,574 INFO  [io.sma.rea.mes.kafka] (smallrye-kafka-producer-thread-1) SRMSG18258: Kafka producer kafka-producer-kogito-usertaskinstances-events, connected to Kafka brokers 'localhost:9092', is configured to write records to 'kogito-usertaskinstances-events'
2024-03-29 11:18:14,579 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-processinstances-events) [Producer clientId=kafka-producer-kogito-processinstances-events] Connection to node -1 (localhost/127.0.0.1:9092) could not be established. Broker may not be available.
2024-03-29 11:18:14,579 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-usertaskinstances-events) [Producer clientId=kafka-producer-kogito-usertaskinstances-events] Connection to node -1 (localhost/127.0.0.1:9092) could not be established. Broker may not be available.
2024-03-29 11:18:14,580 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-processinstances-events) [Producer clientId=kafka-producer-kogito-processinstances-events] Bootstrap broker localhost:9092 (id: -1 rack: null) disconnected
2024-03-29 11:18:14,580 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-usertaskinstances-events) [Producer clientId=kafka-producer-kogito-usertaskinstances-events] Bootstrap broker localhost:9092 (id: -1 rack: null) disconnected
2024-03-29 11:18:14,580 INFO  [io.sma.rea.mes.kafka] (smallrye-kafka-producer-thread-2) SRMSG18258: Kafka producer kafka-producer-kogito-variables-events, connected to Kafka brokers 'localhost:9092', is configured to write records to 'kogito-variables-events'
2024-03-29 11:18:14,581 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-variables-events) [Producer clientId=kafka-producer-kogito-variables-events] Connection to node -1 (localhost/127.0.0.1:9092) could not be established. Broker may not be available.
2024-03-29 11:18:14,581 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-variables-events) [Producer clientId=kafka-producer-kogito-variables-events] Bootstrap broker localhost:9092 (id: -1 rack: null) disconnected
2024-03-29 11:18:14,583 WARN  [io.sma.rea.mes.provider] (main) SRMSG00207: Some components are not connected to either downstream consumers or upstream producers:
        - OutgoingConnector{channel:'kogito-processinstances-events', attribute:'mp.messaging.outgoing.kogito-processinstances-events'} has no upstream
        - OutgoingConnector{channel:'kogito-usertaskinstances-events', attribute:'mp.messaging.outgoing.kogito-usertaskinstances-events'} has no upstream
        - OutgoingConnector{channel:'kogito-variables-events', attribute:'mp.messaging.outgoing.kogito-variables-events'} has no upstream

2024-03-29 11:18:14,629 INFO  [io.quarkus] (main) quarkus-accelerator 1.0.0 on JVM (powered by Quarkus 2.15.3.Final) started in 0.674s. Listening on: http://0.0.0.0:8080
2024-03-29 11:18:14,629 INFO  [io.quarkus] (main) Profile prod activated. 
2024-03-29 11:18:14,630 INFO  [io.quarkus] (main) Installed features: [cdi, kafka-client, resteasy-jackson, smallrye-context-propagation, smallrye-health, smallrye-openapi, smallrye-reactive-messaging, smallrye-reactive-messaging-kafka, swagger-ui, vertx]
2024-03-29 11:18:14,680 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-usertaskinstances-events) [Producer clientId=kafka-producer-kogito-usertaskinstances-events] Connection to node -1 (localhost/127.0.0.1:9092) could not be established. Broker may not be available.
2024-03-29 11:18:14,680 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-processinstances-events) [Producer clientId=kafka-producer-kogito-processinstances-events] Connection to node -1 (localhost/127.0.0.1:9092) could not be established. Broker may not be available.
2024-03-29 11:18:14,680 WARN  [org.apa.kaf.cli.NetworkClient] (kafka-producer-network-thread | kafka-producer-kogito-usertaskinstances-events) [Producer clientId=kafka-producer-kogito-usertaskinstances-events] Bootstrap broker localhost:9092 (id: -1 rack: null) disconnected
```