# Boot Sequence Documentation

---

## Boot Sequence

```
Get info for MainMenu  
1. GET   gfus-cdn.sunborngame.com       → /image/ImageConfig.txt

Request userProtocol
2. POST  gf-passport.sunborngame.com    → /passport/userProtocol

Request Serverlist
3. POST  gf-transit.sunborngame.com     → /index.php

Request version list
4. GET   s3.us-east-2.amazonaws.com     → /sunborn-p1-us/K1TpOZLczan46lSXyXCexbLRUR2eGnXzTMAYzZQP0GpEU7GDrIRFSg.txt
```

---


