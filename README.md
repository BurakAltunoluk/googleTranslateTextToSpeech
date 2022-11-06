# googleTranslateTextToSpeech

# Google Translate Text To Speech - Swift - Xcode

```swift 

var player: AVPlayer?

//----- function --------

   func speechToTextGoogle(language:String, someText: String) {
       
        let textToRead = someText.replacingOccurrences(of: " ", with: "%20")
       
        let url = "https://translate.google.com/translate_tts?ie=UTF-8&q=\(textToRead)&tl=\(language)&total=1&idx=0&textlen=15&tk=350535.255567&client=webapp&prev=input"
        
        guard let url1 = URL.init(string: url)
                        else {
                            return
                    }
        
                    let playerItem = AVPlayerItem.init(url: url1)
                    player = AVPlayer.init(playerItem: playerItem)
                player?.play()
       
    }

//---------------------


//-----Example---------

    @IBAction private func someButtonPressed(_ sender: UIButton) {
        
        speechToTextGoogle(language: "en", someText: "Hello World")
        
    }

```

