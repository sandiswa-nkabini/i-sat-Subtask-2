# i-sat-Subtask-2
string decimalToBinary(int decimal) {   
if (decimal == 0) return "0";   
string binary = "";  
while (decimal > 0) {      
binary = to_string(decimal % 2) + binary;    
decimal /= 2;  
}  
return binary;
}

