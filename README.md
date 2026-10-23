# Ruby - personal Android assistant

Private personal test build. Android 8+ (API 26), no external libraries. Native Android shell with a local WebView interface.

## Install
Install Ruby-1.0.apk on your own Android phone, allowing this download source when Android asks. Debug-signed test build, not a Play Store app. Open Settings in Ruby and paste your own Gemini API key. No key is included. Default model `gemini-2.5-flash` can be changed if your Google project needs another model. Free-tier access depends on Google project, region and quota. Ruby does not subscribe to anything.

## Included
- Hinglish chat with recent session context; Android speech-input activity and Android text-to-speech.
- Snapshot image description and object finder using Gemini; image picker for screenshots. Image uploads require selecting a photo.
- YouTube search, Maps search/navigation, dialer for review, app launch, local audio picker/player, device time/date.
- Optional native Accessibility Service: exact-label tap, back/home/scroll/notifications, focused-field text entry. Explicit confirmation and 5-second delay before controls. No autonomous action planning or event logging.
- WhatsApp chat launch from an international number. Use `tap Voice call` to try the visible call button after enabling Accessibility. This is not contact-name lookup or an auto-call promise. Exact labels depend on app version and language.
- `read screen`: confirm in Ruby, switch apps during the 5-second delay, then visible text is sent to Gemini. Password/editable nodes are skipped, but other sensitive text can still be visible. Do not use on banking or private-chat screens.

## Commands
`time`, `date`, `youtube Neon Labs`, `maps Bhubaneswar`, `navigate to railway station`, `dial +911234567890`, `open WhatsApp`, `open Gemini`, `WhatsApp call +911234567890`, `find keys`, `play music`, `stop`, `tap Voice call`, `type hello`, `read screen`, `back`, `home`, `scroll down`.

## Honest limits
Not a copy of another creator's proprietary source. No always-on wake word or background microphone. No live camera stream or tracking: camera capture returns a preview-sized photo, image picker accepts larger photos. No facial identification. Screen reading extracts visible text, not hidden content or full visual interpretation. No guaranteed cross-app automation, playing YouTube's first result, WhatsApp voice-call completion, app force-close, automatic Gemini prompt submission, or changing secure system settings. AI does not choose or execute arbitrary device actions. Voice engine availability and female voice selection depend on installed Android voices. Cross-app controls need real-phone testing; protected screens may block access. AI responses/vision need the user's key and network and cannot be end-to-end verified without one.

## Privacy/security
Key encrypted with Android Keystore AES-GCM. No backup. No key returned to JavaScript. Requests use Google's HTTPS API directly, with key in request header. Session chat is in memory, not a server. No analytics, ads or background accessibility logs. Optional speech recognition uses the installed Android speech provider. Disable Accessibility when not needed. Android 13+ may require App info > menu > Allow restricted settings for a sideloaded service before enabling it.

## Build
Source tree is in `Ruby-source.zip` in this repo. Extract, then run `chmod +x gradlew && ./gradlew assembleDebug` with JDK 17 and Android SDK 35. The GitHub Actions workflow extracts it and builds manually on demand. Use GitHub's included free allowance only; no paid tools are needed. The local delivered APK and its SHA256 are included separately. Fresh debug keys on other build machines will not update over the first APK without uninstalling; uninstalling removes its local settings.
