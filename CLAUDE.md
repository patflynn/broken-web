# broken.dev Website Guidelines

## Commands
- **Serve locally**: `cd public && python -m http.server` (serves on port 8000)
- **Validate HTML**: `npx html-validator-cli public/index.html`
- **Format HTML**: `npx prettier --write public/index.html`
- **Format CSS**: `npx prettier --write public/styles.css`

## Code Style Guidelines
- **HTML**: Use 4-space indentation, lowercase tags, double quotes for attributes
- **CSS**: Follow BEM naming convention for classes, use 4-space indentation
- **Colors**: Use hex codes (#0f0) for terminal-like theme (green on dark background)
- **Layout**: Maintain terminal-inspired minimalist design
- **ASCII Art**: Preserve box characters and alignment in the pre element
- **Links**: Use default styling inside ASCII art box; cyan color (#0ff)
- **Responsiveness**: Maintain 800px max-width with auto margins

## File Structure
- Keep all website files in the `public/` directory
- Organize any new assets in dedicated folders within public (public/images/, public/js/, etc.)
- Maintain UTF-8 encoding for proper box-drawing characters
- Only files in the public/ directory will be deployed to the website

## Version Control
- Commit messages should be clear and descriptive
- Keep the website focused on promoting the VIBE meditation app
- Always use Pull Request workflow for changes (no direct pushes to main)
- Keep Pull Requests focused on a single task or feature
- PRs should include a clear description of changes and purpose
- **IMPORTANT**: Always pull and rebase with the main branch before creating PRs
  ```
  git fetch origin main
  git rebase origin/main
  ```
- Resolve any conflicts during rebase before pushing to remote