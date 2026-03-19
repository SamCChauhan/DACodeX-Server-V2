# DACodeX-Server-V2
DACodeX-Server-V2 🚀
DACodeX is a multimodal AI Coding Mentor designed for the classroom. It uses the Google Gemini 2.5 Flash model to help students learn programming through Socratic or Direct instruction.

This version is optimized to run as a local server, turning your computer into a hosting hub that can be shared with friends across the internet using ngrok tunneling.

🛠️ Technical Stack
Backend: Python 3.10+

UI Framework: NiceGUI (Web-based interface)

AI Engine: Google GenAI (Gemini API)

Networking: ngrok (Reverse Proxy Tunneling)

✨ Features
Multimodal Capabilities: Upload screenshots of code or error messages for instant analysis.

Pedagogical Modes: Toggle between Socratic (hints & guidance) and Direct (syntax & logic) teaching styles.

Session Management: Archive chat histories and download transcripts as .txt files.

Global Access: Shared via secure HTTPS links, allowing users on any device to connect.

🚀 Quick Start
Clone the Repo:

Bash
git clone https://github.com/YOUR_USERNAME/DACodeX-Server-V2.git
Set Environment Variables:

Bash
export GOOGLE_API_KEY="your_api_key_here"
Run the Server:

Bash
python dacodex_server.py
Start the Tunnel:
In a separate terminal, run:

Bash
ngrok http 8081
🔒 Security Note
This project uses environment variables to handle API keys. Never hardcode your GOOGLE_API_KEY directly into the script before pushing to GitHub. Use a .env file or system environment variables to keep your credentials safe.
