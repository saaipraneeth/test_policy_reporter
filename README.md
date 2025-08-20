# Resume Parser

Extracts names, emails, and skills from PDF/Word resumes using Google's GenAI SDK.

## Quick Start

1. **Install deps**
```bash
pip install -r requirements.txt
```

2. **Get API key** (free)
   - Go to https://makersuite.google.com/app/apikey
   - Create key, copy it

3. **Set up .env**
```
GOOGLE_API_KEY=your_key_here
```

4. **Run it**
   - Drop resumes in `sample_resumes/`
   - Open `resume_parser.ipynb`
   - Run all cells

## What it does

Takes a resume (PDF or Word) → Returns JSON:
```json
{
  "name": "John Doe",
  "email": "john@example.com", 
  "skills": ["Python", "Docker", "AWS"]
}
```

## How it works

1. Extracts text from PDFs/Word docs
2. Sends to Google's Gemini model
3. Falls back to regex if API fails
4. Validates the output

## Files

- `resume_parser.ipynb` - The actual parser
- `sample_resumes/` - Put test files here
- `.env` - Your API key goes here

## Notes

- Works without API key (uses regex fallback, but less accurate)
- Free tier = 1500 requests/min, plenty for most use cases
- Handles any language, not just English

## Issues?

- **No API key?** Still works, just less accurate
- **Rate limited?** Add caching or slow down requests
- **Bad results?** Check if resume is readable/not corrupted

Built for a technical assignment. Feel free to adapt.