---
title: Understanding the session timeouts in Experience Manager Guides
description: Get to know about sessions timeouts in Experience Manager Guides.
feature: Authoring, Publishing
role: User
exl-id: f09b1215-4753-4dfd-89ef-1629257e5efe
TQID: https://experienceleague.adobe.com/nrxkVxSUooy2-08PaUp1pjiH8w2kBBNGC9efarvepbQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Why does Experience Manager Guides sign me out after certain period of time? 

Experience Manager Guides ends a user session after a defined period of inactivity (idle timeout). This auto logout functionality is configured in the Adobe Experience Manager. When the session expires, a pop-up alert is displayed to notify the user about the expired session. This alert restricts the user from making any further changes to the content. 

**How does session timeout work?**

Experience Manager Guides sends a background request `token.json` every 30 seconds to validate the session. If the session is still active, a valid token is returned. If the session has expired due to inactivity, an empty token is returned, and the session is considered inactive.

**What happens when the session expires?**

When an inactive session is detected:

- A pop-up alert appears to notify that you have been signed out. 

    ![](images/sign-out-prompt.png)

- The alert disables all interactions with the application.

- Selecting **OK** refreshes the browser and redirects you to the login page.
- Upon logging in, you are redirected to the last opened page of Experience Manager Guides.

**Next steps**

The session expiry alert helps prevent data loss by restricting you from making changes to the application during an inactive session. To avoid accidental loss of content, it is recommended that you save your work regularly in the Editor, especially before stepping away from your system for an extended period.
