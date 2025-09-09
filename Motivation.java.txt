import java.io.*;
import java.util.*;

public class Motivation {
    public static void main(String[] args) {
        List<String> quotes = new ArrayList<>();

        // Read quotes from file
        try (BufferedReader br = new BufferedReader(new FileReader("quotes.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                quotes.add(line);
            }
        } catch (IOException e) {
            System.out.println("Error reading quotes file.");
            return;
        }

        // Pick a random quote
        if (quotes.size() > 0) {
            Random rand = new Random();
            String randomQuote = quotes.get(rand.nextInt(quotes.size()));
            
            System.out.println("✨ Daily Motivation Generator ✨");
            System.out.println("----------------------------------");
            System.out.println("💡 " + randomQuote);
            System.out.println("----------------------------------");
        } else {
            System.out.println("No quotes found in file.");
        }
    }
}
