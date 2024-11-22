# casting-advanced
```java
class ExpertCastingExercise {
    // Exercise 1: Safe number conversion
    class SafeNumber {
        // Implement safe conversion method
        static Integer toInteger(Object obj) {
            // Handle: String, Double, Long, etc.
            return switch (obj) {
                case String s -> Integer.parseInt(s);
                case Number n -> n.intValue();
                case null -> null;
                default -> throw new IllegalArgumentException();
            };
        }
    }
    
    // Exercise 2: Generic casting
    class Container<T> {
        private Object value;
        
        @SuppressWarnings("unchecked")
        T getValue() {
            // Implement safe generic casting
            return (T)value;  // Why might this be dangerous?
        }
    }
    
    // Exercise 3: Complex hierarchy casting
    interface Readable {}
    interface Writable {}
    class File implements Readable, Writable {}
    class Directory implements Readable {}
    
    void handleFileSystem(Object obj) {
        // Implement type checking and casting
        if (obj instanceof Readable r) {
            // Handle readable things
            if (r instanceof Writable w) {
                // Handle writable things
            }
        }
    }
}
