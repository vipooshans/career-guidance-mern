# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-04-28

### Added

#### Authentication
- Email/Password authentication with JWT
- Google OAuth 2.0 integration using Passport.js
- User registration and login endpoints
- Secure token generation and validation
- Session management

#### Career Guidance
- Career recommendations engine
- Eligibility assessment module
- Alternative career paths suggestions
- Career data seeding scripts
- Integration with Google Gemini AI for career advice

#### Dashboard
- User profile management
- Career progress tracking
- Interactive analytics dashboard
- Document upload functionality (Resume, CV)
- Email notifications with Nodemailer

#### Frontend
- React 18 with Vite build tool
- Responsive UI with Tailwind CSS
- Smooth animations with Framer Motion
- Data visualization with Chart.js
- React Router for navigation
- OAuth login flow with redirect handling

#### Backend
- Express.js REST API
- MongoDB with Mongoose ODM
- CORS middleware configuration
- Morgan HTTP request logging
- Error handling middleware
- Multer for file uploads

#### Database
- MongoDB schemas for users, careers, eligibility
- Data seeding for careers, eligibility, and alternative paths
- Efficient indexing strategies

#### DevOps
- Environment configuration management
- Development and production build scripts
- Nodemon for auto-reload in development
- Live deployment on Vercel

### Security Features
- Password hashing with bcryptjs
- JWT-based authentication
- CORS protection
- Environment variable configuration
- Secure OAuth callback handling

### Known Limitations
- JWT stored in localStorage (should use httpOnly cookies in production)
- No refresh token rotation implemented
- Limited rate limiting on endpoints
- Basic input validation

---

## [Unreleased]

### Planned Features

#### Security Enhancements
- [ ] Implement httpOnly cookies for JWT storage
- [ ] Add refresh token rotation mechanism
- [ ] Rate limiting on authentication endpoints
- [ ] CSRF protection with tokens
- [ ] Input validation with Zod/Joi
- [ ] Request signing for API calls

#### User Experience
- [ ] Dark mode support
- [ ] Multi-language support (i18n)
- [ ] Mobile-responsive improvements
- [ ] Accessibility improvements (WCAG 2.1)
- [ ] Search functionality

#### Features
- [ ] Email verification for new accounts
- [ ] Password reset flow
- [ ] Two-factor authentication (2FA)
- [ ] Resume builder with templates
- [ ] AI-powered resume review
- [ ] Interview preparation module
- [ ] Video interview scheduling
- [ ] Mentor matching system
- [ ] Job board integration

#### Performance
- [ ] Implement caching strategies
- [ ] Database query optimization
- [ ] Image optimization and CDN
- [ ] API response compression
- [ ] Frontend code splitting

#### Testing
- [ ] Unit tests with Jest
- [ ] Integration tests
- [ ] E2E tests with Cypress
- [ ] Component tests with React Testing Library
- [ ] API endpoint coverage

#### Monitoring & Analytics
- [ ] Error tracking with Sentry
- [ ] Application performance monitoring
- [ ] User analytics
- [ ] Server logs aggregation

#### DevOps
- [ ] CI/CD pipeline setup (GitHub Actions)
- [ ] Automated testing on PR
- [ ] Docker containerization
- [ ] Kubernetes deployment
- [ ] Database backup strategies

#### Mobile
- [ ] React Native mobile app
- [ ] iOS deployment
- [ ] Android deployment
- [ ] Push notifications

---

## Versioning

### Version Format: MAJOR.MINOR.PATCH

- **MAJOR**: Incompatible API changes
- **MINOR**: New features (backward compatible)
- **PATCH**: Bug fixes

### Release Cycle

- Releases are published as needed
- Security patches released immediately
- Minor releases every 1-2 months
- Major releases every 6 months

---

## How to Update

### From v0.x to v1.0.0

1. Backup your database
2. Pull latest changes
3. Run `npm install` in both server and client directories
4. Update environment variables if needed
5. Test thoroughly

### Staying Updated

```bash
# Fetch latest changes
git fetch upstream main

# Update your fork
git pull upstream main

# Install any new dependencies
npm install
```

---

## Reporting Issues

Found a bug or want to suggest a feature?
- [Open an Issue](https://github.com/vipooshans/career-guidance-mern/issues)
- [Start a Discussion](https://github.com/vipooshans/career-guidance-mern/discussions)

---

## Contributors

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to contribute.

---

## License

Licensed under [MIT License](LICENSE.md)

---

## Changelog Maintenance

- This file is updated with every release
- Entries are categorized by type: Added, Changed, Deprecated, Removed, Fixed, Security
- Dates follow YYYY-MM-DD format
- Links between versions are maintained
