# i-sat-Subtask-2

#include &lt;iostream&gt;
#include &lt;string&gt;
#include &lt;cmath&gt;
#include &lt;algorithm&gt;
using namespace std;
// Function to convert decimal to binary
string decimalToBinary(int decimal) {
if (decimal == 0) return &quot;0&quot;; // Special case for decimal 0
string binary = &quot;&quot;; // Initialize empty string to store binary representation
while (decimal &gt; 0) {
binary = to_string(decimal % 2) + binary; // Append remainder to binary string   
decimal /= 2; // Divide decimal number by 2
}
return binary;
}
// Function to convert binary to decimal
int binaryToDecimal(string binary) {
int decimal = 0;
int power = 0;
// Iterate over each digit of binary number from right to left
for (int i = binary.length() - 1; i &gt;= 0; i--) {
if (binary[i] == &#39;1&#39;) {
decimal += pow(2, power); // Add 2^power to decimal if digit is &#39;1&#39;
}
power++; // Increment power for next position
}
return decimal;
}
// Function to convert decimal to hexadecimal
string decimalToHexadecimal(int decimal) {
if (decimal == 0) return &quot;0&quot;; // Special case for decimal 0

string hex = &quot;&quot;; // Initialize empty string to store hexadecimal representation
char hexDigits[] = &quot;0123456789ABCDEF&quot;; // Hexadecimal digits
while (decimal &gt; 0) {
hex = hexDigits[decimal % 16] + hex; // Get the corresponding hex digit and append to hex string
decimal /= 16; // Divide decimal number by 16
}
return hex;
}
// Function to convert hexadecimal to decimal
int hexadecimalToDecimal(string hex) {
int decimal = 0;
int power = 0;
// Iterate over each digit of hexadecimal number from right to left
for (int i = hex.length() - 1; i &gt;= 0; i--) {
char digit = hex[i];
int value;
// Convert hexadecimal digit to its corresponding decimal value
if (digit &gt;= &#39;0&#39; &amp;&amp; digit &lt;= &#39;9&#39;) {
value = digit - &#39;0&#39;;
} else if (digit &gt;= &#39;A&#39; &amp;&amp; digit &lt;= &#39;F&#39;) {
value = 10 + (digit - &#39;A&#39;);
} else if (digit &gt;= &#39;a&#39; &amp;&amp; digit &lt;= &#39;f&#39;) {
value = 10 + (digit - &#39;a&#39;);
} else {
value = 0; // In case of invalid hex digit
}
decimal += value * pow(16, power); // Add value * 16^power to decimal
power++; // Increment power for next position
}
return decimal;
}
int main() {
int choice;
cout &lt;&lt; &quot;Conversion Menu:\n&quot;;
cout &lt;&lt; &quot;1. Decimal to Binary\n&quot;;
cout &lt;&lt; &quot;2. Binary to Decimal\n&quot;;
cout &lt;&lt; &quot;3. Decimal to Hexadecimal\n&quot;;
cout &lt;&lt; &quot;4. Hexadecimal to Decimal\n&quot;;
cout &lt;&lt; &quot;Enter your choice (1, 2, 3, or 4): &quot;;
cin &gt;&gt; choice;
if (choice == 1) {
int decimal;
cout &lt;&lt; &quot;Enter a decimal number: &quot;;
cin &gt;&gt; decimal;
string binary = decimalToBinary(decimal);
cout &lt;&lt; &quot;Binary representation: &quot; &lt;&lt; binary &lt;&lt; endl;
} else if (choice == 2) {
string binary;
cout &lt;&lt; &quot;Enter a binary number: &quot;;
cin &gt;&gt; binary;

int decimal = binaryToDecimal(binary);
cout &lt;&lt; &quot;Decimal representation: &quot; &lt;&lt; decimal &lt;&lt; endl;
} else if (choice == 3) {
int decimal;
cout &lt;&lt; &quot;Enter a decimal number: &quot;;
cin &gt;&gt; decimal;
string hex = decimalToHexadecimal(decimal);
cout &lt;&lt; &quot;Hexadecimal representation: &quot; &lt;&lt; hex &lt;&lt; endl;
} else if (choice == 4) {
string hex;
cout &lt;&lt; &quot;Enter a hexadecimal number: &quot;;
cin &gt;&gt; hex;
int decimal = hexadecimalToDecimal(hex);
cout &lt;&lt; &quot;Decimal representation: &quot; &lt;&lt; decimal &lt;&lt; endl;
} else {
cout &lt;&lt; &quot;Invalid choice. Please enter 1, 2, 3, or 4.&quot; &lt;&lt; endl;
}
return 0;
} 

