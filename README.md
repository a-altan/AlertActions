// 3 text box and 1 button init
//Alert Button examples in swift 
import UIKit

class ViewController: UIViewController {

    @IBOutlet weak var userNameText: UITextField!
    @IBOutlet weak var passwordText: UITextField!
    @IBOutlet weak var rePasswordText: UITextField!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
    }


    @IBAction func signUpButton(_ sender: Any) {
        /*
        let alert = UIAlertController(title: "Error!", message: "UserName not found!", preferredStyle: UIAlertController.Style.alert)
        
        let okButton = UIAlertAction(title: "OK", style: UIAlertAction.Style.default) { UIAlertAction in
            // button clicked
            print("button clicked ")
            
        }
        alert.addAction(okButton)
        
        self.present(alert, animated: true, completion: nil)
        */
        if userNameText.text == ""{
            makeAlert(titleInput: "Error ! ", messageInput: "UserName Not Found")
            
        } else if passwordText.text == ""{
            makeAlert(titleInput: "Error ! ", messageInput: "Password Not Found")
            
        } else if passwordText.text != rePasswordText.text{
            makeAlert(titleInput: "Error !", messageInput: "Password Do Not Match")
        } else {
           makeAlert(titleInput: "Succes", messageInput:   "User OK" )
        }
    }

    func makeAlert(titleInput: String, messageInput:String){
        let alert = UIAlertController(title: titleInput,message: messageInput, preferredStyle: UIAlertController.Style.alert)
        let okButton = UIAlertAction(title: "OK", style: UIAlertAction.Style.default, handler: nil)
        alert.addAction(okButton)
        self.present(alert, animated: true, completion: nil)
    }

}
