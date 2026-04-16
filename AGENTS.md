# Project Configuration for Agents

## Build and Verification Commands

This is a static HTML project - no build process required.

### Testing
- Manual testing: Open `src/spese_condominiali.html` in a browser
- Test backup/restore functionality
- Test Excel export
- Test auto-save functionality

### Deployment
- Simply copy `src/spese_condominiali.html` to any web server
- Or use GitLab Pages via `.gitlab-ci.yml`

## Project-Specific Notes

- Single-file HTML application with embedded CSS and JavaScript
- Uses localStorage for data persistence
- Uses SheetJS CDN for Excel export
- No build tools or dependencies required
- Backup files should be stored securely (not in repository)
