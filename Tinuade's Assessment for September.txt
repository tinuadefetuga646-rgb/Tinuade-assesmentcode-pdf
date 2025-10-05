// ASSESMENT FOR THE MONTH OF SEPTEMBER 

// FETUGA TINUADE ELIZABETH

// JAD/TA/25A/BD/001

// Initialising user details
(() => {
 let balance = 10000;
 const correctPin = 2024;
 let transactions = 0;
 let attempts = 0;
 alert("Welcome Beloved User, Put in your Card:");
 let pin = prompt("Enter your Login Pin:");
   
          
// Only One Entry For Pin
while (Number(pin) !== correctPin && attempts < 1) {
 attempts++;
 pin = prompt("It's not the right pin, Try once more otherwise access will be blocked:");
}
// If Pin Is Right Continue with Menu
if (Number(pin) === correctPin) {
 let exit = false;

 while (!exit) {
   let choice = prompt(
       "ATM Menu:\n" +
       "1 - Check Balance\n" +
       "2 - Deposit Money\n" +
       "3 - Withdraw Money\n" +
       "4 - Exit\n\n" +
       "Pick from the choices above(1-4):"
       );
   switch (choice) {
     case "1":
      alert("Your current balance is:" + balance);
      break;
      
      case "2":
       let deposit = prompt("Enter the amount you wish to deposit:");
       deposit = Number(deposit);
       if (!isNaN(deposit) && deposit > 0) {
   balance += deposit;
   transactions++;
   alert("Deposit is a success.\nNew Balance:" + balance);
} else {
    alert(" Deposit Amount Not Possible.");
}
 break;

    case "3":
    let withdraw = prompt("Input Ammount You Wish to Withdraw:");
    withdraw = Number(withdraw);
    if (!isNaN(withdraw) && withdraw > 0) {
        if (withdraw > balance) {
            alert("Insufficient funds.");
        } else {
             balance -= withdraw;
     transactions++;
    alert("Successful Withdrawal.\nNew Balance:" + balance);
   }
     } else {
    alert("Invalid Withdrawal amount.");
  }
   break;
     
     case "4":
   alert("Thank you for using the ATM, Take your Card.\n" +
          "You made " + transactions + " transaction(s).\n" +
          "Final balance:" + balance);
      exit = true;
      break;
   
    default:
      alert("Not a Choice. Enter 1, 2, 3, or 4.");
   }
 }
    } else {
     alert("Access to your account has been blocked. Too many incorrect attempts.");
  }
    })();
  
   

