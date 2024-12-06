When generating or modifying code, strictly adhere to these essential principles and requirements:

**Security First:**
- 🔒 Never store sensitive data (API keys, credentials) in code or version control
- 🛡️ Always validate and sanitize all input data at every layer
- 🔐 Implement proper authentication, authorization, and rate limiting
- ⚠️ Never expose internal errors or sensitive data to clients
- 🔑 Use secure password hashing and proper session management

**Code Quality:**
- 📋 Write clean, maintainable code with proper error handling
- 🎯 Prefer simplicity over complexity in all implementations
- 🧪 Ensure code is testable and includes proper error boundaries
- 📏 Follow TypeScript strict mode and proper type definitions
- 🔍 Implement comprehensive input validation

**Architecture:**
- 🏗️ Maintain clear separation of concerns
- 🚫 Avoid circular dependencies
- 🔄 Use proper versioning for APIs
- 📝 Implement proper logging at all layers
- 🛠️ Follow proper middleware security practices

**Frontend Specific:**
- 🎨 Never store secrets in client-side code
- ♿ Always implement accessibility features (ARIA labels, keyboard navigation)
- 📱 Implement proper code splitting and performance optimization
- 🔄 Use proper state management practices
- 🛡️ Implement CSRF protection and secure session handling

**Backend Specific:**
- 🔒 Never trust client input
- 🛡️ Always implement proper validation and rate limiting
- 📝 Use proper error handling and logging
- 🔑 Implement secure password hashing
- 🔐 Never return sensitive data in responses

**AI Integration:**
- 🤖 Never expose AI API keys
- 🔍 Always validate AI responses
- 🧹 Sanitize all prompts
- 📊 Monitor token usage
- 🔄 Implement retry logic with backoff

For any code you generate or modify, ensure that:
1. All security measures are properly implemented
2. Input validation is thorough and complete
3. Error handling is comprehensive
4. Performance implications are considered
5. Code is clean and maintainable
6. Documentation is clear and complete

Before returning any code, verify that it adheres to these principles and explicitly mention any security considerations or potential issues that should be addressed.
