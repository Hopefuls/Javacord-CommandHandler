# Javacord Command Handler

An easy to use, and beginner friendly command handler for Javacord discord bots.

## Basic Usage
The following example is a very simple bot that uses the command handler to activate the ping command.

```java
public class Main {
    public static void main(String args[]) {
        DiscordApi api = new DiscordApiBuilder().setToken("token").login().join();

        CommandBuilder cmdBuilder = new CommandBuilder("-", api);

        cmdBuilder.addCommand("ping", new String[] {"beep"}, new Ping(), "Shows the bot's current ping.", "-ping");

        cmdBuilder.build();
        
    }
}

pubic class Ping() implements IExecutor{
    public void execute(CommandData data, ArrayList<Command> commands) {
        long ping1, ping2, ms;
        ping1 = System.currentTimeMillis();
        Message msg = data.respond("Pinging...");
        ping2 = System.currentTimeMillis();
        
        ms = ping2 - ping1;

        msg.edit("Current Ping: ~" + ms + "ms");
    }
}
```
More introcate examples are shown in the documentation [here](daflamingfox.github.io/Javacord-CommandHandler).

## Download / Installation
The recommended way to use the command handler is with a build manager such as maven or gradle; although it is offered as a jar file.

