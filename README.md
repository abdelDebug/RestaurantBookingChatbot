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
