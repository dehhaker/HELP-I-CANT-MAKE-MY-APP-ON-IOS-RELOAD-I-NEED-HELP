# HELP-I-CANT-MAKE-MY-APP-ON-IOS-RELOAD-I-NEED-HELP
pLEASE HELP ME. THE CODE UNDERNEATH IS WHAT I HAVE ON XCODEimport UIKit import GoogleMobileAds  class ViewController: UIViewController, GADRewardBasedVideoAdDelegate {      @IBOutlet weak var showAdButton: UIButton!     @IBOutlet weak var logLabel: UILabel!     var rewardBasedAd: GADRewardBasedVideoAd!     override func viewDidLoad() {         super.viewDidLoad()                  showAdButton.isEnabled = false                                   rewardBasedAd = GADRewardBasedVideoAd.sharedInstance()         rewardBasedAd.delegate = self         rewardBasedAd.load(GADRequest(), withAdUnitID: "ca-app-pub-4477422135070128/2664511468")          }       @IBAction func buttonPressed(_ sender: Any) {         showAdButton.isEnabled = false         if rewardBasedAd.isReady {             rewardBasedAd.present(fromRootViewController: self)         }          }     func rewardBasedVideoAdDidOpen(_ rewardBasedVideoAd: GADRewardBasedVideoAd) {         print("An ad opened.\n")     }     func rewardBasedVideoAdDidClose(_ rewardBasedVideoAd: GADRewardBasedVideoAd) {         print("An ad closed.\n")         showAdButton.isEnabled = true     }     func rewardBasedVideoAdDidReceive(_ rewardBasedVideoAd: GADRewardBasedVideoAd) {        print("An ad has loaded.\n")         showAdButton.isEnabled = true             }     func rewardBasedVideoAdDidStartPlaying(_ rewardBasedVideoAd: GADRewardBasedVideoAd) {        print("An ad started playing.\n")     }     func rewardBasedVideoAdWillLeaveApplication(_ rewardBasedVideoAd: GADRewardBasedVideoAd) {        print("An ad caused focus to leave.\n")     }     func rewardBasedVideoAd(_ rewardBasedVideoAd: GADRewardBasedVideoAd, didFailToLoadWithError error: Error) {         print("An ad failed to load.\n")     }     func rewardBasedVideoAd(_ rewardBasedVideoAd: GADRewardBasedVideoAd, didRewardUserWith reward: GADAdReward) {         print("You received \(reward.amount) \reward.type)!\n")     } }
