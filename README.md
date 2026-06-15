# Hey, I'm Ken 👋
 
Engineering leader who ships. Products, the teams behind them, and the systems that keep both standing. My obsession: dragging AI development out of "vibe coding" demos and into production code that survives a real review.
 
**Open to engineering leadership roles in health, hardware, or AI.** Building something there? Let's talk.
 
🎮 [**Claude's Challenge**](https://www.youtube.com/@ClaudesChallenge): I make an AI agent solve Chip's Challenge, the 148-level puzzle classic.
 
## Is your team still vibe coding? Try CRISP.
 
Five things every prompt should hand the model. Framework via [@YagyanshB](https://github.com/YagyanshB).
 
| | Step | What you provide |
| :--: | --- | --- |
| **C** | Context | System, tech stack, and constraints |
| **R** | Requirements | What it must do, and the acceptance criteria |
| **I** | Interface | Inputs, outputs, and contracts |
| **S** | Security | Auth, validation, PII handling |
| **P** | Performance | Latency, scale, and resources |
 
### CRISP in action
 
**Bad prompt:**
 
```
Create an API endpoint to upload profile pictures
```
 
**CRISP prompt:**
 
```
CONTEXT:
- FastAPI app, PostgreSQL (Users table), S3 storage, behind nginx (10MB limit)
 
REQUIREMENTS:
- POST /api/v1/users/{user_id}/avatar
- Accept JPEG/PNG, resize to a 200x200 thumbnail
- Store original + thumbnail in S3, update user.avatar_url
- Return both avatar URLs
 
INTERFACE:
- In: multipart/form-data, 'file' field
- Out: {"avatar_url": "...", "thumbnail_url": "..."}
- Errors: 400 invalid file, 413 too large, 404 user not found
 
SECURITY:
- Valid JWT; user can only update their own avatar (or admin)
- Verify it's a real image via magic bytes, not extension
- Max 5MB; sanitize filename; use a random S3 key
 
PERFORMANCE:
- Resize async (accept upload, process in background)
- <200ms to accept; presigned S3 URL for direct upload if >1MB
```
 
---
 
📓 [Ken Leads on Substack](https://kenleads.substack.com/) · 💼 [LinkedIn](https://www.linkedin.com/in/kmblum/)
