public class main{
    public static void main(String[] args) {
        logger logger1 = logger.getInstance();
        logger logger2 = logger.getInstance();

        logger1.log("This is the first log message.");
        logger2.log("This is the second log message.");

        if (logger1 == logger2) {
            System.out.println("Both logger1 and logger2 refer to the same instance.");
        } else {
            System.out.println("Different instances exist!");
        }
    }
}



public class logger {
    private static logger singleInstance;

    private logger() {
        System.out.println("Logger initialized");
    }

    public static logger getInstance() {
        if (singleInstance == null) {
            singleInstance = new logger();
        }
        return singleInstance;
    }

    public void log(String message) {
        System.out.println("LOG: " + message);
    }
}

OUTPUT:
Logger initialized
LOG: This is the first log message.
LOG: This is the second log message.
Both logger1 and logger2 refer to the same instance.
