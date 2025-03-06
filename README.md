# -occurrences-of-each-character

 import java.util.Map;
import java.util.function.Function;
import java.util.stream.Collectors;

public class CharacterFrequencyStream {
    public static void main(String[] args) {
        String str = "Hello, World!";

        Map<Character, Long> charCountMap = str.chars()  // Convert to IntStream
                .mapToObj(c -> (char) c)  // Convert int to Character
                .collect(Collectors.groupingBy(Function.identity(), Collectors.counting()));

    
        charCountMap.forEach((key, value) -> System.out.println("'" + key + "': " + value));
    }
}
