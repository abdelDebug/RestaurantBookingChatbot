# 🍽️ Restaurant Booking Chatbot (Enhanced Edition)

**`Developed by Dr. Abdelaziz Triki`**

This interactive chatbot demonstrates how to build a conversational restaurant booking system with visual components and enhanced user experience.

## 🚀 Quick Start
1. Run the cell to install dependencies
2. Run the cell to create the chatbot application
3. Run the Streamlit app using ngrok tunnel
4. Click the generated URL to access the booking chatbot

## ✨ New Features
- Modern UI with improved styling and visual hierarchy
- Enhanced date selection with quick date options
- Meal period tabs for intuitive time selection (lunch/dinner)
- Visual indicators for peak hours
- Attractive reservation confirmation screen
- Persistent storage with SQLite database
- Database download capability for Colab environment

## 🗒️ Important Note
- If you encounter a problem with `ngrok`, please create an account first and then insert your personal authtoken using `ngrok.set_auth_token("INSERT_YOUR_KEY_HERE")`.

```
# Import required libraries
from pyngrok import ngrok
import subprocess
import time
import threading

# Start the Streamlit app in the background
def run_streamlit():
    subprocess.Popen(['streamlit', 'run', 'colab_app.py', '--server.port=8501'])

# Start ngrok tunnel
def start_ngrok():
    # Kill any existing ngrok processes
    try:
        subprocess.run(['killall', 'ngrok'], check=False)
    except:
        pass
    
    # **Authenticate ngrok with the provided authtoken**
    ngrok.set_auth_token("INSERT_YOUR_KEY_HERE") 
    
    # Start a new ngrok tunnel to port 8501
    public_url = ngrok.connect(addr='8501', bind_tls=True)
    return public_url

# Run Streamlit in a separate thread
thread = threading.Thread(target=run_streamlit)
thread.daemon = True
thread.start()

# Wait for Streamlit to start up
time.sleep(5)

# Start ngrok and get the public URL
public_url = start_ngrok()
print(f"\n🎉 Restaurant Booking Chatbot is now running!")
print(f"\n🔗 Access your chatbot at this URL: {public_url}")
print("\n📝 Note: This link will only be valid while this notebook is running.")
print("\nClick the link above to open the Restaurant Booking Chatbot in a new tab.")
print("\n--- Features and Instructions ---")
print("✓ Book a new table by typing 'book a table' or clicking the Book button")
print("✓ Manage existing reservations by typing 'manage my bookings'")
print("✓ Cancel reservations by selecting a reservation and choosing cancel")
print("✓ Download the database using the button at the bottom of the app")
print("\nThe chatbot will guide you through each step of the process.")
print("\nKeep this notebook running to maintain your access to the chatbot.")

  
