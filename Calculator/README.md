import UIKit

class ViewController: UIViewController {

@IBOutlet weak var display: UILabel! //UILabel is a type

var userIsInTheMiddleOfTypingANumber: Bool = false


@IBAction func appendDigit(sender: UIButton) {

//        adding a property to tell if the user is pushing the button


// sender currnet title is a property for a button type is infered to be same type as sender.currentTitle
//        digit is my own variable but I can still use the option key to scroll over my own variable or constant, just like I would do a swift variable or constant, then hover the curser over the variable or constant, in this case digit, let the question mark hover then click to get information ie, type in this case of digit, it is String? which is an optional string
//        in this case digit is an optional type
//        an optional can only be two things
//        1. nil (which means one thing in Swift - the value of an optional not set
//        2. something
//        whatever is to the left of the question mark is the type of the something that the optional is set to
//        it looks like this String?
//        it's not a string that can be nil it's an optional that can be a string
//        we might call it an optional string but it's really just an optional that can be a string
//        if you ?hover over .currentTitle you see get, which means read-only you cannot set the currentTitle here
//        let digit = sender.currentTitle
//        this time we add the exlamation point at the end of the optional to "unpack" it, now when we ?hover over digit we see it is a String
let digit = sender.currentTitle!
if userIsInTheMiddleOfTypingANumber {
//        this prints digit is Optional("5") if 5 is pressed on the Simulator
//        now this prints 5 if 5 is pressed on the Simulator
print("digit is \(digit)")
//        this appends all the digit's pressed to the string that is being displayed int the outlet labeled display
//        you must use the ! to unpack the display.text optional so you can append the string digit to it
display.text = display.text! + digit
}   else    {
display.text = digit
userIsInTheMiddleOfTypingANumber = true
}
}
}