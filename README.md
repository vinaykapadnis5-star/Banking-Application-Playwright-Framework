import com.microsoft.playwright.*;

public class BankingTest {

    public static void main(String[] args) {

        try (Playwright playwright = Playwright.create()) {

            Browser browser = playwright.chromium().launch(
                    new BrowserType.LaunchOptions().setHeadless(false));

            Page page = browser.newPage();

            // Open Banking Website
            page.navigate("https://demo.guru99.com/V4/");

            System.out.println("Page Title: " + page.title());

            if (page.title().contains("Guru99")) {
                System.out.println("Banking Test Passed");
            } else {
                System.out.println("Banking Test Failed");
            }

            browser.close();
        }
    }
}
