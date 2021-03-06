# Sink.actorRefWithAck

Send the elements from the stream to an `ActorRef` which must then acknowledge reception after completing a message, to provide back pressure onto the sink.

@ref[Sink stages](../index.md#sink-stages)

## Description

Send the elements from the stream to an `ActorRef` which must then acknowledge reception after completing a message,
to provide back pressure onto the sink.

## Example

Actor to be interacted with: 

Scala
:   @@snip [IntegrationDocSpec.scala]($code$/scala/docs/stream/IntegrationDocSpec.scala) { #actorRefWithAck-actor }

Java
:   @@snip [IntegrationDocTest.java]($code$/java/jdocs/stream/IntegrationDocTest.java) { #actorRefWithAck-actor }

Using the `actorRefWithAck` operator with the above actor:

Scala
:   @@snip [IntegrationDocSpec.scala]($code$/scala/docs/stream/IntegrationDocSpec.scala) { #actorRefWithAck }

Java
:   @@snip [IntegrationDocTest.java]($code$/java/jdocs/stream/IntegrationDocTest.java) { #actorRefWithAck }

## Reactive Streams semantics 

@@@div { .callout }

**cancels** when the actor terminates

**backpressures** when the actor acknowledgement has not arrived

@@@

