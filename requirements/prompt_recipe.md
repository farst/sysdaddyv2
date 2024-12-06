# SysDaddy v2 Implementation Guide

## System Role and Principles

> This implementation guide serves as a comprehensive reference for building a secure, maintainable, and scalable system. Follow all warnings and requirements strictly to ensure the highest quality implementation.

### Core Responsibilities
- Write clean, defensive, and maintainable code
- Identify and prevent security vulnerabilities
- Ensure proper error handling and validation
- Maintain consistency across the codebase
- Consider performance implications
- Document thoroughly
- Follow best practices for testing

### Fundamental Principles
- Always prefer simplicity over complexity
- Never trust user input
- Always validate data at every layer
- Implement proper error handling
- Use defensive programming techniques
- Keep security at the forefront
- Maintain backward compatibility
- Consider scalability implications
- Document thoroughly
- Write testable code

---

## Implementation Tasks

### Phase 1: Project Setup

#### Task 1: Monorepo Setup

**CRITICAL WARNINGS:**
- Never store sensitive information in version control
- Never use default configurations without review
- Avoid development-only shortcuts
- Never disable security features for convenience

**Requirements:**
```
MUST:
- Initialize Nx workspace with strict configuration
- Configure ESLint and Prettier with security rules
- Implement git hooks for pre-commit checks
- Set up separate environments

NEVER:
- Commit sensitive data
- Skip security checks
- Use default configurations
- Disable security features
```

**Steps:**
1. Initialize Nx workspace:
   ```bash
   npx create-nx-workspace@latest cascade --preset=ts
   ```
2. Configure workspace:
   - Set up TypeScript strict mode
   - Configure path aliases
   - Implement shared libraries
3. Setup security measures:
   - Configure git hooks
   - Implement security scanning
   - Set up dependency auditing

#### Task 2: Directory Structure

**CRITICAL WARNINGS:**
- Never mix concerns between layers
- Avoid circular dependencies
- Prevent direct database access from presentation layer
- Never expose internal APIs unintentionally

**Project Structure:**
```
/project-root
├── /apps
│   ├── /frontend
│   └── /backend
├── /libs
│   ├── /shared-types
│   ├── /shared-utils
│   └── /shared-constants
├── /tools
└── /docs
```

#### Task 3: Environment Configuration

**CRITICAL WARNINGS:**
- Never store secrets in code
- Avoid environment configuration in version control
- Never use production credentials in development
- Prevent credential leakage

**Environment Files:**
```
├── .env.example
├── .env.development
├── .env.staging
└── .env.production
```

---

### Phase 2: Frontend Implementation

#### Task 4: Next.js Setup

**CRITICAL WARNINGS:**
- Never expose sensitive configurations
- Avoid client-side secrets
- Never skip TypeScript strict checks
- Prevent bundle bloat

**Project Structure:**
```
/frontend
├── /pages
├── /components
├── /hooks
├── /services
├── /utils
└── /types
```

#### Task 5: Frontend Dependencies

**CRITICAL WARNINGS:**
- Never use outdated dependencies
- Avoid unnecessary dependencies
- Never skip security audits
- Prevent dependency conflicts

**Required Dependencies:**
```
MUST:
- next-auth for secure authentication
- axios with proper interceptors
- react-query for state management
- Material-UI with proper theming

NEVER:
- Skip dependency updates
- Use unvetted packages
- Leave security vulnerabilities
- Mix incompatible versions
```

#### Task 6: Authentication Implementation

**CRITICAL WARNINGS:**
- Never store sensitive auth data client-side
- Avoid client-side token manipulation
- Never skip token validation
- Prevent auth bypass attempts
- Never store passwords in plain text
- Avoid session fixation

**Implementation Requirements:**
```
MUST:
- Implement secure token handling
- Use HTTP-only cookies
- Configure proper session management
- Implement MFA support
- Set up proper password policies
- Create secure reset flows

NEVER:
- Store tokens in localStorage
- Skip token validation
- Use client-side encryption
- Leave auth endpoints unprotected
```

**Authentication Components:**
```
/auth
├── /components
│   ├── LoginForm
│   ├── RegisterForm
│   ├── ResetPassword
│   └── MFASetup
├── /hooks
│   ├── useAuth
│   └── useSession
└── /services
    ├── authService
    └── tokenService
```

#### Task 7: UI Component Library

**CRITICAL WARNINGS:**
- Never skip accessibility features
- Avoid inconsistent styling
- Never ignore component performance
- Prevent prop drilling
- Never skip input validation
- Avoid direct DOM manipulation

**Implementation Requirements:**
```
MUST:
- Implement ARIA attributes
- Create consistent theming
- Test component performance
- Document all components
- Implement proper validation
- Use React refs appropriately

NEVER:
- Skip accessibility testing
- Mix different design patterns
- Leave components untested
- Create tight coupling
```

**Component Structure:**
```
/components
├── /atoms
├── /molecules
├── /organisms
├── /templates
└── /pages
```

#### Task 8: Interview Management System

**CRITICAL WARNINGS:**
- Never expose sensitive interview data
- Avoid real-time sync issues
- Never skip data validation
- Prevent unauthorized access
- Never lose interview progress
- Avoid state management issues

**Implementation Requirements:**
```
MUST:
- Implement secure data handling
- Use proper websocket security
- Create robust error handling
- Implement auto-save
- Set up proper permissions
- Create audit logging

NEVER:
- Store sensitive data client-side
- Skip connection security
- Leave sessions unmonitored
- Ignore error states
```

**Interview System Structure:**
```
/interview
├── /components
│   ├── TemplateBuilder
│   ├── InterviewConductor
│   └── ResultsViewer
├── /hooks
│   ├── useInterview
│   └── useTemplate
└── /services
    ├── interviewService
    └── templateService
```

#### Task 9: AI Integration

**CRITICAL WARNINGS:**
- Never expose AI API keys
- Avoid unlimited token consumption
- Never trust AI responses blindly
- Prevent prompt injection
- Never store sensitive data in prompts
- Avoid response manipulation

**Implementation Requirements:**
```
MUST:
- Implement proper rate limiting
- Validate all AI responses
- Monitor token usage
- Implement retry logic
- Sanitize all prompts
- Log AI interactions

NEVER:
- Expose API credentials
- Skip response validation
- Trust AI output blindly
- Allow arbitrary prompts
```

**AI Integration Structure:**
```
/ai
├── /services
│   ├── aiService
│   └── promptService
├── /hooks
│   ├── useAI
│   └── usePrompt
└── /utils
    ├── promptBuilder
    └── responseValidator
```

---

### Phase 3: Backend Implementation

#### Task 10: Express Backend Setup

**CRITICAL WARNINGS:**
- Never expose internal errors
- Avoid security misconfiguration
- Never skip middleware security
- Prevent unauthorized access

**Backend Structure:**
```
/src
├── /config
├── /middleware
├── /models
├── /controllers
├── /services
└── /utils
```

#### Task 11: User Management System

**CRITICAL WARNINGS:**
- Never store plain passwords
- Avoid weak password policies
- Never skip input sanitization
- Prevent privilege escalation
- Never expose user data
- Avoid session fixation

**Implementation Requirements:**
```
MUST:
- Use strong password hashing
- Implement proper validation
- Create secure sessions
- Set up role management
- Monitor auth attempts
- Implement rate limiting

NEVER:
- Store sensitive data plaintext
- Skip password validation
- Trust client roles
- Leave sessions unprotected
```

#### Task 12: API Endpoint Implementation

**CRITICAL WARNINGS:**
- Never expose internal endpoints
- Avoid excessive endpoint creation
- Never skip input validation
- Prevent parameter pollution
- Never trust HTTP headers blindly
- Avoid response data leakage

**Implementation Requirements:**
```
MUST:
- Implement proper versioning
- Validate all inputs
- Use proper HTTP methods
- Document all endpoints
- Implement rate limiting
- Set up proper error responses

NEVER:
- Skip parameter validation
- Return sensitive data
- Leave endpoints undocumented
- Mix API versions
```

**API Structure:**
```
/api
├── /v1
│   ├── /auth
│   ├── /users
│   ├── /interviews
│   └── /templates
└── /middleware
    ├── validation
    ├── authentication
    └── rateLimit
```

---

## Implementation Notes for Cascade

### Security Checklist
- Input validation
- Authentication checks
- Authorization validation
- Error handling
- Data sanitization
- Security headers
- Rate limiting
- Logging

### Quality Assurance Steps
1. Code review requirements
2. Testing requirements
3. Documentation requirements
4. Security review requirements
5. Performance review requirements

### Maintenance Guidelines
- Regular security updates
- Dependency audits
- Performance monitoring
- Documentation updates

### Testing Infrastructure
- Implement unit tests
- Create integration tests
- Set up E2E testing
- Test security measures
- Create test fixtures
- Monitor test coverage

### Documentation
- Document all APIs
- Create setup guides
- Document architecture
- Maintain changelogs
- Create user guides
- Document security measures

### Final Notes
- All code must pass security scanning
- Regular security audits required
- Maintain updated documentation
- Regular performance testing
- Monitor system health
- Keep dependencies updated