# reddit-gaeilge
A place to store tools for scraping /r/gaeilge

### Set up
Create an account on [reddit](https://www.reddit.com/) and select the `create another app` on the reddit preferences page: (https://www.reddit.com/prefs/apps).

This will give you the `<reddit_id>` and `<reddit_secret>` values that you will need for authorisation.

### Scraping comments
```bash
cd subreddit-comments-dl

# Install requirements
pip install -r requirements.txt

# Download the gaeilge comments of the last 30 submissions
python src/subreddit_downloader.py gaeilge --batch-size 10 --laps 3 --reddit-id <reddit_id> --reddit-secret <reddit_secret> --reddit-username <reddit_username>

# If the script was terminated, use the `--utc-before` flag to fetch submissions before the Unix timestamp of the last submission that was scraped, e.g.:
python src/subreddit_downloader.py gaeilge --batch-size 10 --laps 3 --reddit-id <reddit_id> --reddit-secret <reddit_secret> --reddit-username <reddit_username> --utc-before 1662044617

# Build the dataset, the results will be under `./dataset/` path
python src/dataset_builder.py 
```
