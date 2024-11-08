#include <stdio.h>

void convertCurrency(float amount, int fromCurrency, int toCurrency) {
    float convertedAmount;
    
    // Conversion rates (example rates, update as per current rates)
    float usdToInr = 83.0;
    float eurToInr = 90.0;
    float gbpToInr = 105.0;
    
    switch(fromCurrency) {
        case 1: // USD to other currencies
            if(toCurrency == 1)
                printf("You chose the same currency!\n");
            else if(toCurrency == 2)
                convertedAmount = amount * usdToInr;
            else if(toCurrency == 3)
                convertedAmount = amount * (usdToInr / eurToInr);
            else if(toCurrency == 4)
                convertedAmount = amount * (usdToInr / gbpToInr);
            break;
        case 2: // INR to other currencies
            if(toCurrency == 1)
                convertedAmount = amount / usdToInr;
            else if(toCurrency == 2)
                printf("You chose the same currency!\n");
            else if(toCurrency == 3)
                convertedAmount = amount / eurToInr;
            else if(toCurrency == 4)
                convertedAmount = amount / gbpToInr;
            break;
        case 3: // EUR to other currencies
            if(toCurrency == 1)
                convertedAmount = amount * (eurToInr / usdToInr);
            else if(toCurrency == 2)
                convertedAmount = amount * eurToInr;
            else if(toCurrency == 3)
                printf("You chose the same currency!\n");
            else if(toCurrency == 4)
                convertedAmount = amount * (eurToInr / gbpToInr);
            break;
        case 4: // GBP to other currencies
            if(toCurrency == 1)
                convertedAmount = amount * (gbpToInr / usdToInr);
            else if(toCurrency == 2)
                convertedAmount = amount * gbpToInr;
            else if(toCurrency == 3)
                convertedAmount = amount * (gbpToInr / eurToInr);
            else if(toCurrency == 4)
                printf("You chose the same currency!\n");
            break;
        default:
            printf("Invalid input.\n");
            return;
    }

    if (fromCurrency != toCurrency)
        printf("Converted amount: %.2f\n", convertedAmount);
}

int main() {
    float amount;
    int fromCurrency, toCurrency;

    printf("Currency Converter\n");
    printf("1. USD (Dollar)\n");
    printf("2. INR (Rupees)\n");
    printf("3. EUR (Euro)\n");
    printf("4. GBP (Pound)\n");

    printf("Enter the amount: ");
    scanf("%f", &amount);

    printf("Choose the currency you want to convert from (1-4): ");
    scanf("%d", &fromCurrency);

    printf("Choose the currency you want to convert to (1-4): ");
    scanf("%d", &toCurrency);

    convertCurrency(amount, fromCurrency, toCurrency);

    return 0;
}
