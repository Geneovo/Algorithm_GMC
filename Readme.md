This algorithm reads a sentence character by character until it encounters a period (.). It determines:
1) The length of the sentence (total number of characters, including the period).
2) The number of words (assuming the words are separated by single space).
3) The number of vowels (a, e, i, o, u, both uppercase and lowercase).

Pseudocode:
BEGIN
    // Initialize counters
    length_counter := 0
    word_counter := 0
    vowel_counter := 0
    previous_char := ' '  // To track previous character for better word counting

    // Read characters until the period is encountered
    REPEAT
        READ character
        length_counter := length_counter + 1

        // Check if the character is a vowel (both lowercase and uppercase)
        IF character IN {'a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U'} THEN
            vowel_counter := vowel_counter + 1
        END_IF

        // Check if a new word starts (space followed by a letter)
        IF previous_char = ' ' AND character != ' ' AND character != '.' THEN
            word_counter := word_counter + 1
        END_IF

        // Store current character as previous for next iteration
        previous_char := character
    UNTIL character = '.'

    // Output the results
    WRITE length_counter
    WRITE word_counter
    WRITE vowel_counter
END
