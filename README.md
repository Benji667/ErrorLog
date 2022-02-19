# Error Log

Logging errors is one of the unavoidable important task when you develop applications. 

The *Logger* provides a way for applications to configure different log *Handlers* and a way to send the log messages to the appropriate destination.

Internally, the message is turned into a *Log Record* object and routed to a *Handler* object registered for this *Logger*. The *Handler* will then use a *Serializer* to turn the LogRecord into a string and output that string.

The Error Log library takes a modular approach and offers several categories of components: *Logger*, *Handler*, and *Serializer*.

- *Logger* exposes the interface that application code directly uses. It keeps track of a set of Handler and send the log records to the appropriate destination.
- *Handler* is set of methods to effectively output (write/display) log records. Handler filters out log records based on their Level.
- *Serializer* specifies the layout of log records in the final output.

## Log Levels

Not all log messages are created equal. Depending of the importance of the log message, developer define a Level to his Log messages.

- *DEBUG* : Detailed information, typically of interest only when diagnosing problems.
- *INFO* : Confirmation that things are working as expected.
- *WARNING* : An indication that something unexpected happened. The application is still working as expected.
- *ERROR* : Due to a more serious problem, the application has not been able to perform some tasks.
- *CRITICAL* : A serious error, indicating that the application itself may be unable to continue running.

When you set a logging level to an Handler, you’re telling the library you want to handle all events from that level on up. If you set the log level to INFO, it will include INFO, WARNING, ERROR, and CRITICAL messages. DEBUG messages will not be included here.

## Handlers

Handlers are concrete implementation of methods to output log events. 

- File Handler: record each log message in a file. 
- User Event Handler: fires LabVIEW User Events for each log message.

![ErrorLog_1](https://github.com/Benji667/ErrorLog/blob/e5cb40c8963b157d7db4b25fe0937077b1bd07cf/docs/ErrorLog_1.gif)