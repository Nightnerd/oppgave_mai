# oppgave_mai

Pseudokode:

    Funksjon find_lowest_sum(matrix):
    rows = antall rader i matrix
    cols = antall kolonner i matrix
    dp = ny matrise med størrelse rows x cols
    
    dp[0][0] = matrix[0][0]
    For i fra 1 til rows:
        dp[i][0] = dp[i - 1][0] + matrix[i][0]
    For j fra 1 til cols:
        dp[0][j] = dp[0][j - 1] + matrix[0][j]
        
    For i fra 1 til rows:
        For j fra 1 til cols:
            dp[i][j] = minimum av dp[i - 1][j] og dp[i][j - 1] + matrix[i][j]
    
    path = tom liste
    i = rows - 1
    j = cols - 1
    Mens i > 0 eller j > 0:
        Legg til matrix[i][j] i path
        Hvis i = 0:
            Reduser j med 1
        Ellers hvis j = 0:
            Reduser i med 1
        Ellers:
            Hvis dp[i - 1][j] < dp[i][j - 1]:
                Reduser i med 1
            Ellers:
                Reduser j med 1
    Legg til matrix[0][0] i path
    
    Returner dp[rows - 1][cols - 1] og reverser path

    Funksjon find_highest_sum(matrix):
    (samme som find_lowest_sum, bare med maksimum i stedet for minimum)

    Array1 = [...]
    Array2 = [...]
    Array3 = [...]
    Array4 = [...]
    Array5 = [...]
    Array6 = [...]

    Skriv "Array 1"
    laveste_sum, laveste_path = find_lowest_sum(Array1)
    høyeste_sum, høyeste_path = find_highest_sum(Array1)
    Skriv "Laveste Sum:", laveste_sum
    Skriv "Sti med Laveste Sum:", laveste_path
    Skriv "Høyeste Sum:", høyeste_sum
    Skriv "Sti med Høyeste Sum:", høyeste_path

    (Samme for Array2, Array3, Array4, Array5, Array6)
