# 🔐 PrivateBChecks Collection

<div align="center">
  <img src="https://img.shields.io/badge/BurpSuite-BCheck-orange" alt="BurpSuite BCheck"/>
  <img src="https://img.shields.io/badge/Security-Testing-red" alt="Security Testing"/>
  <img src="https://img.shields.io/badge/Author-CyberTechAjju-blue" alt="Author"/>
  <img src="https://img.shields.io/badge/Web-Security-brightgreen" alt="Web Security"/>
  <img src="https://img.shields.io/badge/Hacking-Tools-blueviolet" alt="Hacking Tools"/>
  <br>
  <img src="https://img.shields.io/badge/Language-BCheck-yellow" alt="Language"/>
  <img src="https://img.shields.io/badge/Penetration-Testing-success" alt="Penetration Testing"/>
  <img src="https://img.shields.io/badge/Status-Active-success" alt="Status"/>
</div>

<p align="center">
  <img src="https://raw.githubusercontent.com/sindresorhus/awesome/main/media/logo.svg" alt="Awesome" width="400">
</p>

<pre align="center">
  ██████╗ ██████╗ ██╗██╗   ██╗ █████╗ ████████╗███████╗██████╗  ██████╗██╗  ██╗███████╗ ██████╗██╗  ██╗███████╗
  ██╔══██╗██╔══██╗██║██║   ██║██╔══██╗╚══██╔══╝██╔════╝██╔══██╗██╔════╝██║  ██║██╔════╝██╔════╝██║ ██╔╝██╔════╝
  ██████╔╝██████╔╝██║██║   ██║███████║   ██║   █████╗  ██████╔╝██║     ███████║█████╗  ██║     █████╔╝ ███████╗
  ██╔═══╝ ██╔══██╗██║╚██╗ ██╔╝██╔══██║   ██║   ██╔══╝  ██╔══██╗██║     ██╔══██║██╔══╝  ██║     ██╔═██╗ ╚════██║
  ██║     ██║  ██║██║ ╚████╔╝ ██║  ██║   ██║   ███████╗██████╔╝╚██████╗██║  ██║███████╗╚██████╗██║  ██╗███████║
  ╚═╝     ╚═╝  ╚═╝╚═╝  ╚═══╝  ╚═╝  ╚═╝   ╚═╝   ╚══════╝╚═════╝  ╚═════╝╚═╝  ╚═╝╚══════╝ ╚═════╝╚═╝  ╚═╝╚══════╝
</pre>

<div align="center">
  <h3>[ Developed with ❤️ by CyberTechAjju ]</h3>
</div>

## 📜 Overview

A sophisticated collection of custom BCheck scripts for Burp Suite to enhance your web application security testing capabilities. These scripts automate various security checks including bypass techniques, vulnerability detection, and security control testing. Designed for professional penetration testers, bug bounty hunters, and security enthusiasts to streamline their workflow and increase efficiency.

## 🔍 Collection Contents

### 403 & 401 Bypass Techniques

| Script | Description |
|--------|-------------|
| `403 Bypass Comprehensive Techniques.bcheck` | Comprehensive 403 bypass testing using header manipulation, URL obfuscation, method overrides, and custom headers. Implements multiple techniques in a single scan. |
| `403  401 Header Bypass via IP.bcheck` | Attempts potential bypass methods to access responses originally returning 403 or 401 status codes by replacing specific headers with various IP payloads. Based on research from multiple security researchers. |
| `403-429 bypass using HTTP Header.bcheck` | Attempts to bypass 403/429 using the HTTP headers with local IP address. Targets rate limiting and access control mechanisms. |

### Rate Limiting & Middleware Checks

| Script | Description |
|--------|-------------|
| `Rate limiter detected.bcheck` | Check response to detect the presence of different forms of rate limiter. Identifies various rate limiting implementations including those from major cloud providers. |
| `CVE-2025-29927 - Nextjs middleware bypass.bcheck` | Checks for differences in responses when using different x-middleware-subrequest header paths. Targets Next.js applications with potentially vulnerable middleware configurations. |

### Path & File Checks

| Script | Description |
|--------|-------------|
| `Path-level.bcheck` | Tests for exposed backup files with various extensions (.bak, .back, .backup, .old). Identifies potentially sensitive files that may have been left on the server. |

## 💻 Technical Details

### How These BChecks Work

Each BCheck script follows a similar pattern:

```
metadata:
    language: v2-beta
    name: "Script Name"
    description: "What the script does"
    author: "CyberTechAjju"
    tags: "relevant", "tags"

define:
    # Variables and constants used in the check

run for each:
    # Arrays of values to iterate through during testing

given request/response then
    # Logic to execute the security test
    # Conditions to evaluate
    # Actions to take based on results
```

### Advanced Features

- **Header Manipulation**: Tests various HTTP headers with different payloads
- **IP Spoofing Detection**: Identifies when applications trust client-provided IP addresses
- **Rate Limit Bypass**: Attempts to circumvent rate limiting mechanisms
- **Path Traversal**: Tests for directory traversal vulnerabilities
- **Middleware Bypass**: Targets application middleware for security weaknesses

## 🚀 Installation

1. Download the BCheck files from this repository
2. Open Burp Suite Professional
3. Navigate to the Extensions tab
4. Select the BChecks sub-tab
5. Click "Add" and select the downloaded BCheck files
6. Enable the checks you want to use in your scans

## 💡 Usage

### Basic Usage

1. Configure your Burp Suite scan settings
2. Ensure the relevant BChecks are enabled
3. Start your scan against the target application
4. Review the scan results for potential vulnerabilities

### Advanced Usage

For more targeted testing:

```bash
# Example of using BChecks with Burp Suite CLI
java -jar burpsuite_pro.jar --project-file=project.burp --config-file=config.json
```

## 🔧 Customization

Each BCheck can be customized to fit your specific testing needs:

1. Open the BCheck file in a text editor
2. Modify the arrays of test values
3. Adjust the severity and confidence levels
4. Add additional test cases as needed
5. Save and reload in Burp Suite

## 🛡️ Defensive Countermeasures

To protect against the vulnerabilities these BChecks detect:

1. Implement proper server-side validation
2. Don't trust client-provided headers for security decisions
3. Use consistent access control mechanisms
4. Properly configure rate limiting
5. Sanitize and validate all user input
6. Implement proper error handling

## 🌐 Community Resources

### Similar BCheck Collections

<details>
<summary>Click to expand the list of related BCheck repositories</summary>

- [PortSwigger/BChecks](https://github.com/PortSwigger/BChecks)
- [NetSPIWillD/BChecks](https://github.com/NetSPIWillD/BChecks)
- [lisandre-com/BChecks](https://github.com/lisandre-com/BChecks)
- [beishanxueyuan/BChecks](https://github.com/beishanxueyuan/BChecks)
- [nullfuzz-pentest/bchecks-templates](https://github.com/nullfuzz-pentest/bchecks-templates)
- [cyberK9/BChecksFTW](https://github.com/cyberK9/BChecksFTW)
- [IAmRoot0/BCheck-Rules](https://github.com/IAmRoot0/BCheck-Rules)
- [0xm4v3rick/Burp-BChecks](https://github.com/0xm4v3rick/Burp-BChecks)
- [buggysolid/bchecks](https://github.com/buggysolid/bchecks)
- [vrechson/copy-to-bcheck](https://github.com/vrechson/copy-to-bcheck)
- [MrW0l05zyn/bchecks](https://github.com/MrW0l05zyn/bchecks)
- [Hannah-PortSwigger/SaveBchecksToFile](https://github.com/Hannah-PortSwigger/SaveBchecksToFile)
- [jayluxferro/BChecks](https://github.com/jayluxferro/BChecks)
- [jimiss/bchecks](https://github.com/jimiss/bchecks)
- [QdghJ/burpsuite-bchecks](https://github.com/QdghJ/burpsuite-bchecks)
- [yeswehack/BCheck-Burp-scripts](https://github.com/yeswehack/BCheck-Burp-scripts)
- [CosasDePuma/Hacktomation](https://github.com/CosasDePuma/Hacktomation)
- [KaustubhRai/bchecks](https://github.com/KaustubhRai/bchecks)
- [nithisshs/Custom-Bchecks](https://github.com/nithisshs/Custom-Bchecks)
- [vmnguyen/bcheck-collection](https://github.com/vmnguyen/bcheck-collection)
- [0x0msg/Bcheck_Collection](https://github.com/0x0msg/Bcheck_Collection)
- [j3ssie/custom-bcheck-scan](https://github.com/j3ssie/custom-bcheck-scan)
- [AliAhdy/Burp-Suite-BChecks---OWASP-ASVS-V4.0.3](https://github.com/AliAhdy/Burp-Suite-BChecks---OWASP-ASVS-V4.0.3)
- [BuffaloWill/BChecksPublic](https://github.com/BuffaloWill/BChecksPublic)
- [HektikSec/BChecks](https://github.com/HektikSec/BChecks)
- [kjeevesh/bchecks](https://github.com/kjeevesh/bchecks)
- [10up/wp-bcheck](https://github.com/10up/wp-bcheck)
- [kalhoralireza/morvarid-bcheck](https://github.com/kalhoralireza/morvarid-bcheck)
</details>

## 📚 Learning Resources

- [BCheck Official Documentation](https://portswigger.net/burp/documentation/scanner/bchecks)

## ⚠️ Disclaimer

These scripts are provided for legitimate security testing purposes only. Always ensure you have proper authorization before testing any systems. The author is not responsible for any misuse or damage caused by these scripts.

```
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 👨‍💻 Author

<div align="center">
  <img src="https://avatars.githubusercontent.com/u/120666627?v=4" width="100px" alt="CyberTechAjju"/>
  <br>
  <h3>Created with ❤️ by <a href="https://github.com/cyberajju">CyberTechAjju</a></h3>
  <p>Security Researcher | Bug Hunter | Penetration Tester</p>
</div>

## 📄 License

This project is available for use under the MIT License.

## 🤝 Contributing

Contributions are welcome! If you have additional BCheck scripts or improvements to existing ones:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📊 Stats

![GitHub stars](https://img.shields.io/github/stars/CyberTechAjju/PrivateBChecks?style=social)
![GitHub forks](https://img.shields.io/github/forks/CyberTechAjju/PrivateBChecks?style=social)
![GitHub issues](https://img.shields.io/github/issues/CyberTechAjju/PrivateBChecks?style=social)

---

<div align="center">
  <p>
    <img src="https://img.shields.io/badge/-%3E%20H4CK%20TH3%20PL4N3T%20%3C-black?style=for-the-badge"/>
  </p>
  <p>If you find these scripts useful, please consider giving this repository a ⭐</p>
  <pre>
  ┌───────────────────────────────────────────────────────────────┐
  │                                                               │
  │   "The quieter you become, the more you are able to hear."    │
  │                                           - Kali Linux        │
  │                                                               │
  └───────────────────────────────────────────────────────────────┘
  </pre>
  <p>Keep Learning Keep Hacking! 🚀</p>
</div> 
