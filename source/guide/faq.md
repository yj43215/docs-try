---
title: FAQ
type: guide
order: 10*
---
Frequently asked questions about setup and LS usage.
## Image/audio/resource loading error while labeling
The most common mistake while resource loading is CORS (Cross-Origin Resource Sharing) problem or Cross Domain. When you are trying to fetch a picture from external hosting it could be blocked by security reasons. Go to browser console (Ctrl + Shift + i for Chrome) and check errors there. Typically, this problem is solved by the external host setup.
<div style="margin:auto; text-align:center; width:100%"><img src="/images/cors-error.png" style="opacity: 0.7"/></div>
<div style="margin:auto; text-align:center; width:100%"><img src="/images/cors-error2.png" style="opacity: 0.7"/></div>
- If you have an access to the hosting server as admin then you need to allow CORS for the web server. For nginx you can try to add these lines to /etc/nginx/nginx.conf into your location section: 
- If you use Amazon S3 with LS read this manual.
- If you use Google Storage with LS read this manual.
- Not every host supports CORS setup, but you may to try find these settings in the admin area. 
## How to make pre-annotations & pre-labeling
You can import pre-annotated tasks into LS. Pre-annotations will be automatically shown on Labeling page. Prepare your tasks with predictions field which is very similar to completions and then import your tasks to LS. Read more about task format and predictions.
```yaml
[{
  "data": {
    "my_text": "Opossum is great" 
  },

  "predictions": [{
    "result": [{
      "from_name": "sentiment_class",
      "to_name": "message",
      "type": "choices",
      "value": {
        "choices": ["Neutral"]
      }
    }]
  }]
}]
```
