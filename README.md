# TN_ipqs_lookup
Looks up IPQS Fraud/Risk Scores and posts to tracking number record in CTM


# CTM/IPQualityScore Tracking Number Checker (Command-Line Edition)

This tool looks up all tracking numbers in your CTM account, checks each with IPQualityScore,
sends results as custom fields to CTM, and gives you clear, color-free terminal summaries.

## Requirements
- Python 3.7+
- Internet connection
- Your CTM account API Access Key & Secret Key https://app.calltrackingmetrics.com/accounts/edit#account-api

- Your IPQualityScore "phone" API Key https://www.ipqualityscore.com/user/api-keys



***IMPORTANT***
: Create custom fields saved to tracking number (does not need to be set to save to activity on create) with the following API names:
tn_risk_fraud_last_checked ; field type DATE
tn_fraud_score_over_90 ; field type On/Off switch
tn_flagged_as_risky ; field type On/Off switch
tn_flagged_as_spammer ; field type On/Off switch
tn_found_in_leaked_db ; field type On/Off switch
***/IMPORTANT***
–
definitions of IPQS results can be found here: https://www.ipqualityscore.com/documentation/phone-number-validation-api/response-parameters
–

## Setup (First Time)
*Unzip to documents folder*
1. Open Terminal.
2. Navigate to the folder:
   ```
   cd ~/Documents/TN_Commandline
   ```
3. Install dependencies:
   ```
   pip3 install -r requirements.txt
   ```

## Running the Check
**On Mac:**

- Run this in Terminal after navigating to    cd ~/Documents/TN_Commandline
  ```
  python3 tracking_check.py
  ```

## What Happens Next
- The first time, you'll be prompted in the terminal for your CTM and IPQS keys and account ID. (Settings are saved in `tracking_config.json`.)
- The script will fetch your tracking numbers, check them, and push results back to CTM.
- In the terminal, you’ll see clear output:
  - What numbers are flagged as risky, fraudulent, or spammer
  - What was posted/updated
  - Any errors

## To Reconfigure or Start Over
Just delete `tracking_config.json` (or run and re-enter keys as prompted).

## To Check All Numbers Regardless of Time (Override)
Run:
```
python3 tracking_check.py --override-24h
```

## Log/Results for Advanced Use
- Results and logs are saved to text files in the same directory (JSON files)

---
**Support:**
If you have trouble or suggestions, contact your script provider.
