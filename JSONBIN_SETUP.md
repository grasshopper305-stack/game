# JSONBin Setup Guide for World's Hardest Game

## Why JSONBin?
JSONBin.io is a **FREE** JSON storage service - perfect for saving your leaderboard in the cloud! No complex setup, just one API key!

## Step-by-Step Setup (2 minutes!)

### 1. Create a Free JSONBin Account

1. Go to https://jsonbin.io/
2. Click "Sign Up" in the top right
3. Enter your email and create a password
4. Verify your email
5. Log in

### 2. Get Your API Key

1. After logging in, you'll see your dashboard
2. Click on "API Keys" in the left menu
3. You'll see your **X-Master-Key** - this is your API key!
4. Copy it (it looks like: `$2b$10$abc123...xyz789`)

### 3. Update Your Game Code

1. Open `index.html` in a text editor
2. Find this line near the top of the `<script>` tag:
```javascript
const JSONBIN_API_KEY = 'YOUR_JSONBIN_API_KEY'; // Replace with your API key
```

3. Replace `YOUR_JSONBIN_API_KEY` with your actual API key:
```javascript
const JSONBIN_API_KEY = '$2b$10$abc123...xyz789'; // Your real API key
```

4. Save the file

### 4. Deploy and Test!

1. Upload your updated `index.html` to GitHub/Vercel
2. Open your game in a browser
3. Play and complete a level
4. Check the browser console (F12) - you should see: 
   - "Created new JSONBin! ID: ..."
   - "Leaderboard saved to JSONBin!"
5. **IMPORTANT:** Copy the Bin ID from the console message
6. Open `index.html` again and find this line:
```javascript
const JSONBIN_BIN_ID = 'YOUR_BIN_ID'; // Will be created automatically on first run
```
7. Replace `YOUR_BIN_ID` with the ID from console:
```javascript
const JSONBIN_BIN_ID = '67a8c1d9acd3cb34a8b5f2a1'; // Your actual Bin ID
```
8. Save and re-deploy

### 5. Verify Global Leaderboard

1. Open the game in a **different browser** or **incognito window**
2. Play and check the leaderboard
3. You should see scores from both browsers! 🎉

## How It Works

- **First run:** Creates a new "bin" (database) automatically
- **Every score update:** Saves to JSONBin cloud
- **On page load:** Fetches latest leaderboard from cloud
- **Merges:** Combines cloud data with local data for best results

## Free Tier Limits

JSONBin free tier includes:
- **Unlimited bins** (databases)
- **100,000 API requests/month** (way more than you need!)
- **No credit card required**
- **Forever free**

Perfect for your game! 🎮

## Troubleshooting

**"Failed to load from JSONBin" in console:**
- Make sure your API key is correct
- Check you're using the X-Master-Key (not X-Access-Key)

**Leaderboard not syncing:**
- Make sure you added the Bin ID after first run
- Check browser console (F12) for error messages
- Verify you have internet connection

**Want to see your data?**
- Go to https://jsonbin.io/
- Click "Bins" in the left menu
- You'll see your leaderboard bin and can view/edit the data!

## Alternative Services (if you prefer)

If JSONBin doesn't work for you, these are similar:

1. **Firebase** (Google) - More features, slightly more setup
2. **Supabase** - Open source Firebase alternative
3. **MongoDB Atlas** - Free database tier

All work similarly - you just need an API key!

## Questions?

Check the browser console (F12) for error messages. Most issues are:
1. API key not replaced
2. Bin ID not added after first run
3. Internet connection issues

Enjoy your global leaderboard! 🏆
