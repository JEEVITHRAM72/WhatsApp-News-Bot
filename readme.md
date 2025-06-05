# 📱 WhatsApp News Bot

An automated Python bot that fetches the latest Indian news and sends updates via WhatsApp using the Twilio API.

## ✨ Features

- 🗞️ Fetches top 3 Indian news articles from NewsData.io
- 📱 Sends formatted updates via WhatsApp
- 🔄 Runs continuously (currently every 3 seconds)
- 🎯 Simple and straightforward implementation

## 🚀 Quick Start

### Prerequisites

- Python 3.7+
- NewsData.io API account (free tier available)
- Twilio account with WhatsApp sandbox enabled

### Installation

1. **Clone the project**
   ```bash
   git clone <repository-url>
   cd whatsapp-news-bot
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Update credentials in the code**
   - Edit `news_bot.py`
   - Replace the API keys and phone numbers with your own

4. **Run the bot**
   ```bash
   python news_bot.py
   ```

## 🔧 Configuration

### API Credentials (Edit in news_bot.py)

```python
NEWSDATA_API_KEY = "your_newsdata_api_key_here" 
TWILIO_SID = "your_twilio_account_sid_here"
TWILIO_AUTH_TOKEN = "your_twilio_auth_token_here"
FROM_WHATSAPP_NUMBER = "whatsapp:+14155238886"  # Twilio sandbox number
TO_WHATSAPP_NUMBER = "whatsapp:+your_phone_number_here"
```

### Getting API Credentials

#### NewsData.io Setup
1. Visit [newsdata.io](https://newsdata.io)
2. Create a free account
3. Copy your API key from the dashboard
4. Free tier: 200 requests/day

#### Twilio WhatsApp Setup
1. Create account at [twilio.com](https://twilio.com)
2. Go to Console → Messaging → WhatsApp sandbox
3. Follow the setup instructions
4. Get your Account SID and Auth Token
5. Note the sandbox WhatsApp number

## 📋 Usage

### Basic Usage
```bash
python news_bot.py
```

### Customizing News Categories
Edit the API URL in `get_latest_news()` function:
```python
# Available categories: business, entertainment, sports, technology, health, science
url = f"https://newsdata.io/api/1/news?apikey={API_KEY}&country=in&category=technology"
```

### Changing Update Frequency
Edit the `time.sleep(60)` line in `news_bot.py`:
```python
time.sleep(3600)  # 1 hour
time.sleep(1800)  # 30 minutes  
time.sleep(21600) # 6 hours
```

## 📱 Sample Output

```
📰 News Update - 2025-06-05 14:30:00

🗞 *PM Modi Announces New Digital India Initiative*
📍 PTI | 🕒 2025-06-05 10:30:00
🔗 https://example.com/news1

🗞 *Indian Economy Shows Strong Growth in Q2*
📍 Economic Times | 🕒 2025-06-05 09:15:00
🔗 https://example.com/news2

🗞 *Mumbai Metro Line 3 Opens to Public*
📍 Mumbai Mirror | 🕒 2025-06-05 08:45:00
🔗 https://example.com/news3
```

## 🗂️ Project Structure

```
whatsapp-news-bot/
├── news_bot.py          # Main application (your original code)
├── requirements.txt     # Python dependencies
├── .gitignore          # Git ignore rules
├── README.md           # Project documentation
└── LICENSE             # MIT License
```

## ⚠️ Important Notes

- **Update Frequency**: Currently set to 3 seconds - you may want to change `time.sleep(3)` to `time.sleep(3600)` for hourly updates
- **API Limits**: NewsData.io free tier allows 200 requests/day
- **Security**: Consider moving API keys to environment variables for production use

## ⚠️ Error Handling

The bot handles common issues:
- Network timeouts
- API rate limits
- Invalid credentials
- WhatsApp delivery failures
- Malformed news data

## 🛡️ Security Best Practices

- ✅ Use environment variables for credentials
- ✅ Never commit `.env` file to version control
- ✅ Regularly rotate API keys
- ✅ Monitor API usage and costs
- ✅ Use HTTPS for all API calls

## 📊 Rate Limits & Costs

### NewsData.io
- **Free Tier**: 200 requests/day
- **Cost**: $0 for basic usage
- **Current Usage**: 1 request per update interval

### Twilio WhatsApp
- **Sandbox**: Free for testing
- **Production**: ~$0.005 per message
- **Current Usage**: 1 message per update interval

## 🚨 Troubleshooting

### Common Issues

**"No news found" error**
- Check API key validity
- Verify internet connection
- Check NewsData.io service status

**WhatsApp messages not sending**
- Verify Twilio credentials
- Check WhatsApp sandbox setup
- Ensure phone number format includes `whatsapp:` prefix

**API rate limit exceeded**
- Increase `UPDATE_INTERVAL`
- Upgrade NewsData.io plan
- Monitor daily usage

### Debug Mode
Enable detailed logging:
```python
logging.getLogger().setLevel(logging.DEBUG)
```

## 🔮 Future Enhancements

- [ ] Add error handling for API failures
- [ ] Use environment variables for security
- [ ] Add logging for debugging
- [ ] Implement duplicate article detection
- [ ] Multiple recipient support
- [ ] Web dashboard for configuration

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚖️ Disclaimer

- This project is for educational purposes
- Ensure compliance with NewsData.io and Twilio Terms of Service
- Respect WhatsApp Business Policy
- Follow local data protection regulations
- Monitor usage to avoid excessive costs

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📞 Support

For issues and questions:
- Check the troubleshooting section
- Review application logs
- Open an issue on GitHub

---

Made with ❤️ for automated news delivery
BY
   JEEVITHRAM N K
   jeevithramm@gmail.com
