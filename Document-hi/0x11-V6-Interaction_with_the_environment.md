# V6: सुरक्षा सत्यापन की आवश्यकता

## उद्देश्य नियंत्रण

इस समूह में नियंत्रण सुरक्षित करता है तथा App सुरक्षित तरीके से प्लेटफार्म API और स्टैंडर्ड कंपोनेंट्स का उपयोग करता है। इसके अतिरिक्त नियंत्रण APPLICATION (IPC)  के बीच कम्युनिकेशन को कवर करता है।.

## सुरक्षा सत्यापन की आवश्यकता

| # | MSTG-ID | Description | L1 | L2 |
| -- | -------- | ---------------------- | - | - |
| **6.1** | MSTG-PLATFORM-1 | यह App केवल आवश्यक कम से कम सेट को Permission देता है. | ✓ | ✓ |
| **6.2** | MSTG-PLATFORM-2 | External Sources और Users के सभी इनपुट मान्य किए गए हैं और यदि आवश्यक सेनीटाइज भी हो तो इसमें UI, IPC जैसे कि intents data, Custom URLs और Network Source के माध्यम से प्राप्त डाटा शामिल है.| ✓ | ✓ |
| **6.3** | MSTG-PLATFORM-3 | यह App Custom URL योजनाओं के माध्यम से Sensitive Functionality को export नहीं करता है जब तक कि यह Mechanisms ठीक से सुरक्षित ना हो. | ✓ | ✓ |
| **6.4** | MSTG-PLATFORM-4 | यह App  IPC  सुविधाओं के माध्यम से Sensitive Functionality को export नहीं करता है। तथा जब तक कि इन  Mechanisms को ठीक से सुरक्षित नहीं किया जाता है. | ✓ | ✓ |
| **6.5** | MSTG-PLATFORM-5 | Java Script को वेब व्यू मे डिसएबल नहीं किया जाता, जब तक की वह स्पष्ट रूप से आवश्यक नहीं हो. | ✓ | ✓ |
| **6.6** | MSTG-PLATFORM-6 | वेब व्यू को केवल Protocols Handlers के कम से कम set की अनुमति देने के लिए कॉन्फ़िगर किया जाता है ( केवल https सपोर्टेड). Potentially, Dangerous Handlers, जैसे  File, Tel और App id  डिसएबल होते हैं. | ✓ | ✓ |
| **6.7** | MSTG-PLATFORM-7 | यदि App के Native Method के  किसी वेब व्यू के संपर्क में है, तो वेरीफाइड करे कि वेब व्यू केवल App Package के अंदर मौजूद Java Script को रेंडर करता है. | ✓ | ✓ |
| **6.8** | MSTG-PLATFORM-8 | Object destination, यदि कोई हो, सुरक्षित serialisation APIs का उपयोग करके कार्यन्वित  किया जाता है. | ✓ | ✓ |
| **6.9** | MSTG-PLATFORM-9 | यह App खुद को Scree Overlay Attack से बचाता है (सिर्फ Android के लिए) |  | ✓ |
| **6.10** | MSTG-PLATFORM-10 | वेब व्यू के clear होने से पहले एक वेब व्यू का Cache, storage और Loaded Resources (Java Script )  को clear होना चाहिए. |  | ✓ |
| **6.11** | MSTG-PLATFORM-11 | जब भी से Sensitive Data इंटर किया जाता है तो verify करें कि App कस्टम third party  keyboard के उपयोग को रोके. | | ✓ |

## सन्दर्भ

OWASP Mobile Security Testing Guide, इस खंड में सूचीबद्ध आवश्यकताओ  की पुष्टि करने के लिए विस्तृत निर्देश प्रदान करती है.

- Android: Testing Platform Interaction - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05h-Testing-Platform-Interaction.md>
- iOS: Testing Platform Interaction - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06h-Testing-Platform-Interaction.md>

अधिक जानकारी के लिए यह भी देखें:

- OWASP Mobile Top 10: M1 (Improper Platform Usage) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m1-improper-platform-usage>
- OWASP Mobile Top 10: M7 (Poor Code Quality) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m7-client-code-quality>
- CWE 20 (Improper Input Validation) - <https://cwe.mitre.org/data/definitions/20.html>
- CWE 79 (Improper Neutralization of Input During Web Page Generation) - <https://cwe.mitre.org/data/definitions/79.html>
- CWE 200 (Information Leak / Disclosure) - <https://cwe.mitre.org/data/definitions/200.html>
- CWE 250 (Execution with Unnecessary Privileges) - <https://cwe.mitre.org/data/definitions/250.html>
- CWE 672 (Operation on a Resource after Expiration or Release) - <https://cwe.mitre.org/data/definitions/672.html>
- CWE 749 (Exposed Dangerous Method or Function) - <https://cwe.mitre.org/data/definitions/749.html>
- CWE 772 (Missing Release of Resource after Effective Lifetime) - <https://cwe.mitre.org/data/definitions/772.html>
- CWE 920 (Improper Restriction of Power Consumption) - <https://cwe.mitre.org/data/definitions/920.html>
- CWE 925 (Improper Verification of Intent by Broadcast Receiver) - <https://cwe.mitre.org/data/definitions/925.html>
- CWE 926 (Improper Export of Android Application Components) - <https://cwe.mitre.org/data/definitions/926.html>
- CWE 927 (Use of Implicit Intent for Sensitive Communication) - <https://cwe.mitre.org/data/definitions/927.html>
- CWE 939 (Improper Authorization in Handler for Custom URL Scheme) - <https://cwe.mitre.org/data/definitions/939.html>
