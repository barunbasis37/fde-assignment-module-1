# Contributing to FDE Landing Pages

Thank you for your interest in contributing to the FDE Landing Pages project! This document provides guidelines and instructions for contributing.

## Getting Started

1. **Fork the repository** on GitHub
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/fde-assignment-module-1.git
   cd fde-assignment-module-1
   ```
3. **Create a feature branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Project Structure

```
.
├── index-sonnet.html      # Navy & blue professional design
├── index-opus.html        # Warm off-white & orange design
├── index-Haiku.html       # Purple & white minimalist design
├── .github/
│   └── pull_request_template.md
├── CONTRIBUTING.md
└── README.md
```

## Making Changes

### HTML & CSS Guidelines

- **Responsive first**: Test at 375px, 768px, 1024px, and 1440px
- **Dark mode support**: Use `prefers-color-scheme: dark` media queries
- **Accessibility**: 
  - WCAG AA contrast minimum (4.5:1 for text)
  - Semantic HTML structure
  - Keyboard navigation support
  - Focus states clearly visible
  - Aria labels where appropriate
- **No external dependencies**: Keep everything in a single HTML file with embedded CSS
- **Performance**: Minimize animations, optimize any images

### Design Principles

Each page should have a distinct visual identity while maintaining:
- Clear hierarchy and readability
- Consistent spacing and alignment
- Smooth transitions (use `transition` property, not animations where possible)
- Respect for `prefers-reduced-motion`

### Code Style

- Use 2-space indentation
- Meaningful class and ID names
- CSS variables for consistent theming
- Comments for complex logic only

## Testing Before Submission

Before submitting a pull request, ensure:

- [ ] Page works on mobile (375px), tablet (768px), and desktop (1440px)
- [ ] Dark mode renders correctly
- [ ] No horizontal scroll on mobile
- [ ] All links work
- [ ] Form elements are accessible (44px+ touch targets)
- [ ] Keyboard navigation works (Tab, Enter, Space)
- [ ] Focus indicators are visible
- [ ] No console errors

### Local Testing

Start a local server in the project directory:
```bash
python -m http.server 8000
```

Then visit `http://localhost:8000/index-page-name.html`

## Commit Messages

Write clear, descriptive commit messages:

```
Add dark mode support to index-opus.html

- Add @media (prefers-color-scheme: dark) override
- Update CSS variables for dark palette
- Test on mobile and desktop viewports
```

**Commit format**: Present tense, concise subject line, detailed body if needed.

## Pull Request Process

1. **Create a pull request** from your feature branch to `main`
2. **Fill out the PR template** completely
3. **Link related issues** if applicable
4. **Include screenshots** for design changes
5. **Describe testing** performed
6. **Be responsive** to review feedback

## Pages Overview

### index-sonnet.html
- **Style**: Professional, enterprise-focused
- **Colors**: Navy (#0F172A), blue accents, light backgrounds
- **Best for**: Companies wanting a trustworthy, corporate appearance

### index-opus.html
- **Style**: Warm, approachable
- **Colors**: Off-white (#FAF8F5), orange accents (#C2410C)
- **Features**: Terminal-style deployment log visual
- **Best for**: Modern, forward-thinking SaaS companies

### index-Haiku.html
- **Style**: Minimalist, modern
- **Colors**: Purple accents (#6D28D9), clean whites
- **Features**: Timeline-based process layout
- **Best for**: Startups and tech-focused companies

## Reporting Issues

Found a bug? Please create an issue with:
- Clear title describing the problem
- Steps to reproduce
- Expected vs. actual behavior
- Screenshots if applicable
- Browser/device information

## Questions?

Feel free to open an issue for questions or discussions about the project.

## License

By contributing, you agree that your contributions will be licensed under the same license as the project.

---

Happy contributing! 🚀
