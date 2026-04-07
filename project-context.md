---
project_name: 'TAI Bank Mobile App'
user_name: 'tai'
date: '2026-04-07'
sections_completed: ['technology_stack', 'critical_implementation_rules', 'functional_requirements', 'compliance_requirements', 'mobile_app_requirements']
existing_patterns_found: 48
---

# Project Context for AI Agents - TAI Bank Mobile Banking Application

_This file contains critical rules and patterns that AI agents must follow when implementing code in this project. Focus on unobvious details that agents might otherwise miss, especially fintech compliance, mobile app constraints, and cross-platform consistency requirements._

---

## Technology Stack & Versions

### Mobile App Framework
- **React Native** for cross-platform iOS/Android development (iOS 14+ and Android API 24+)
- **React** with **Vite** for web companion application with identical feature parity
- **Tailwind CSS** for consistent styling across platforms
- **localStorage** for client-side data persistence (no backend initially)

### Development Tools
- **BMAD Framework** - AI-driven development methodology with specialized modules for fintech development
- **Vite** for build tooling and development server with hot module replacement
- **ES Modules** for modern JavaScript/TypeScript imports

### Platform Requirements
- **iOS**: iOS 14+ with backward compatibility to iOS 13+ (degraded features)
- **Android**: Android API 24+ (Android 7.0+) with backward compatibility to API 23+
- **Web**: Progressive Web App (PWA) with browser push notification support

## Critical Implementation Rules

### Fintech Compliance & Security
- **PCI DSS Level 1**: All payment data must be tokenized and never stored in localStorage
- **AES-256 Encryption**: All sensitive data must be encrypted at rest and in transit
- **KYC/AML Compliance**: Identity verification and suspicious activity monitoring required
- **Multi-Factor Authentication**: Required for all financial transactions
- **Session Management**: Sessions must timeout within 15 minutes of inactivity
- **Failed Login Limits**: Maximum 5 failed attempts per hour per account

### Mobile App Constraints
- **Offline Mode**: Core functionality must work offline (balance viewing, recent transactions, saved payees)
- **Device Permissions**: Biometric auth, camera, location, NFC, push notifications, contacts (optional)
- **Push Notifications**: Transaction alerts, security alerts, bill reminders, account updates
- **Cross-Platform Consistency**: Identical functionality and UI across iOS, Android, and web
- **Performance Requirements**: 60fps animations, <2s transaction processing, <1s balance queries

### Data Management
- **localStorage Only**: All data stored in browser localStorage (no backend for MVP)
- **JSON-Serializable**: All data structures must be JSON-compatible
- **Data Synchronization**: Automatic sync when connectivity restored with conflict resolution
- **Offline Queue**: Transactions queue for offline execution when connectivity returns

### Component Architecture
- **React Native Components**: Use platform-specific optimizations for native features
- **Shared Business Logic**: Common logic between mobile and web platforms
- **Tailwind Integration**: Consistent styling with utility-first approach
- **Accessibility**: WCAG 2.1 AA compliance with screen reader support

## Functional Requirements by Capability Area

### Account Management (FR1-FR6)
- FR1: Biometric onboarding for personal and business accounts
- FR2: Separate business banking account management
- FR3: Consolidated account balance and transaction history view
- FR4: External account linking for unified financial view
- FR5: Account security preferences and settings management
- FR6: Offline access to basic account information

### Transaction Processing (FR7-FR12)
- FR7: Domestic peer-to-peer money transfers
- FR8: Recurring bill payment automation
- FR9: Bulk payment operations for business accounts
- FR10: Offline transaction queuing for execution when connected
- FR11: Real-time transaction status and confirmations
- FR12: Transaction cancellation and modification capabilities

### Payment Services (FR13-FR18)
- FR13: One-tap group payments to multiple recipients
- FR14: Invoice-based payment requests and processing
- FR15: International transfers with exchange rate display
- FR16: Apple Pay/Google Pay contactless payment integration
- FR17: Camera-based check deposit functionality
- FR18: ATM and branch locator services

### Business Banking (FR19-FR24)
- FR19: Business invoice generation and sending
- FR20: Separate business expense tracking from personal finances
- FR21: Accounting software integration (QuickBooks, Xero, etc.)
- FR22: Cash flow projections and analytics dashboards
- FR23: Vendor payment relationship management
- FR24: Business financial report generation

### AI & Insights (FR25-FR30)
- FR25: AI-powered transaction categorization
- FR26: Proactive spending pattern insights and alerts
- FR27: Personalized budgeting recommendations
- FR28: Predictive cash flow analysis
- FR29: Automated financial optimization suggestions
- FR30: Voice-activated financial commands and queries

### Security & Authentication (FR31-FR36)
- FR31: Biometric authentication (fingerprint, face ID, voice)
- FR32: Multi-factor authentication settings management
- FR33: Account security event monitoring and alerts
- FR34: Account freeze capabilities for suspected compromise
- FR35: Device authorization and access management
- FR36: Privacy settings and data management controls

### Cross-Platform Experience (FR37-FR42)
- FR37: Identical functionality across iOS, Android, and web platforms
- FR38: Real-time data synchronization across all devices
- FR39: Consistent push notification experience across platforms
- FR40: Session continuity when switching between devices
- FR41: Offline functionality on mobile devices
- FR42: Consistent performance across all platform implementations

### Compliance & Regulatory (FR43-FR48)
- FR43: KYC verification process completion
- FR44: Consent management for data processing and privacy
- FR45: Transparent fee structure display and management
- FR46: Suspicious transaction reporting capabilities
- FR47: Data portability and account closure processes
- FR48: Regulatory compliance information and disclosure access

## Non-Functional Requirements

### Performance Standards
- Transaction processing: <2 seconds completion
- Account balance queries: <1 second response
- Application launch/login: <3 seconds
- Cross-platform synchronization: <5 seconds after connectivity restoration
- System scalability: Support 10x user growth (5K to 50K users) with <10% performance degradation

### Security Standards
- AES-256 encryption for all data at rest and in transit
- PCI DSS Level 1 compliance for payment processing
- SOC 2 Type II compliance for operational security
- Multi-factor authentication for all financial operations
- Session timeout within 15 minutes of inactivity
- Failed login attempt limits (5 per hour per account)

### Reliability Standards
- 99.999% uptime SLA for core banking operations
- Automatic failover within 30 seconds of system failures
- Zero data loss guarantee for committed transactions
- Data backup and recovery within 4 hours of incidents

### Compliance Standards
- WCAG 2.1 AA accessibility compliance
- KYC/AML transaction monitoring and reporting
- GDPR compliance for EU users with data portability
- CCPA compliance for California residents
- Regional banking regulations and licensing requirements

## Mobile App Specific Requirements

### Device Permissions & Capabilities
- **Biometric Authentication**: Fingerprint/Face ID for login and transaction authorization
- **Camera Access**: Check deposit, QR code scanning, identity document capture
- **Location Services**: ATM/branch finding, transaction geolocation verification
- **NFC Access**: Contactless payment integration (Apple Pay/Google Pay)
- **Push Notifications**: Transaction alerts, security notifications, bill reminders
- **Contacts Access**: Optional recipient auto-complete for transfers

### Offline Mode Capabilities
- View account balances and recent transaction history (30 days)
- Access saved payees and payment templates
- View account alerts and cached notifications
- Basic account security settings management
- Transaction queuing for execution when connectivity restored

### Push Notification Strategy
- **Transaction Alerts**: Immediate notifications for all account activity
- **Security Alerts**: Login attempts, password changes, suspicious activity
- **Bill Payment Reminders**: Upcoming due dates and payment confirmations
- **Account Updates**: Balance alerts, interest credits, fee notifications
- **Marketing Communications**: Optional promotional offers and product updates

### Platform-Specific Optimizations
- **iOS**: Apple Push Notification Service (APNS) with rich notifications
- **Android**: Firebase Cloud Messaging (FCM) with notification channels
- **Web**: Browser push notifications with PWA support and service workers

## User Journey Personas

### Emma (24, UX Designer) - Digital Native
- Prioritizes seamless, intuitive mobile experience
- Values AI insights and proactive financial guidance
- Expects instant biometric onboarding and cross-platform consistency
- Needs one-tap group payments and transparent fee structures

### Marcus (35, Marketing Manager) - Busy Professional
- Requires voice-activated commands and automation
- Values time-saving features like recurring payments
- Needs business expense tracking and categorization
- Expects reliable offline functionality for travel

### Sarah (42, Boutique Owner) - Small Business Owner
- Needs separate business/personal account management
- Requires accounting software integration
- Values bulk payment processing and invoicing features
- Expects cash flow projections and business analytics

## Development Priorities & Constraints

### Security-First Architecture
- Compliance requirements built into every component
- Security testing including penetration testing required
- Regular security updates and patches mandatory
- Zero-trust security model with defense in depth

### Cross-Platform Consistency
- Identical user experience across iOS, Android, and web
- Shared business logic with platform-specific UI optimizations
- Consistent performance and feature parity across platforms
- Unified design system and component library

### AI Integration Requirements
- Transaction categorization using machine learning
- Proactive spending insights and recommendations
- Voice command processing and natural language understanding
- Predictive analytics for cash flow and budgeting

### Testing Strategy
- Comprehensive security testing and penetration testing
- Cross-platform compatibility testing across device matrix
- Performance testing under various network conditions
- Compliance testing with regulatory requirements
- Accessibility testing for WCAG 2.1 AA compliance

## Framework Integration Guidelines

### BMAD Framework Usage
- Leverage appropriate BMAD modules for fintech development tasks
- Use `core/` for general utilities and shared components
- Use `wds/` for web development and PWA features
- Use `tea/` for comprehensive testing strategies
- Follow established patterns in each module's configuration

### Code Quality Standards
- Clean, readable, maintainable code following React/React Native best practices
- Comprehensive error handling and user feedback
- Proper TypeScript typing for all data structures and API contracts
- Modular architecture with clear separation of concerns
- Extensive unit and integration test coverage

### Deployment Strategy
- Phased rollout starting with beta testing and feature flags
- Continuous monitoring and alerting for security incidents
- Automated testing and quality gates for all deployments
- Rollback capabilities for rapid incident response
- Regular compliance audits and security assessments