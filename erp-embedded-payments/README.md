# ERP Embedded Payments - Interactive Demo

## 📋 Overview

This directory contains interactive prototypes and documentation for the **ERP Embedded Payments** initiative - a Q4 2025 strategic project to enable direct payment execution from ERP systems (ARI, Defontana) without leaving the workflow.

## 🎯 Initiative Summary

**Vision**: Enable finance teams to complete payment jobs-to-be-done without ever leaving their ERP workspace

**Primary Job-to-be-Done**: "Help me process mass payments without leaving my ERP workflow"

**Target Users**: Finance managers and accounting teams using ARI and Defontana ERPs

**Business Impact**:
- 25-40% increase in payment volume capture
- 90% reduction in workflow interruption time
- <30 seconds payment completion (vs 5-10 minutes manual process)

## 📁 Directory Structure

```
erp-embedded-payments/
├── README.md                    # This file
├── index.html                   # Interactive MVP demo
├── bpmn-flow.html              # Payment flow visualization
└── docs/                       # Reference documentation
    ├── HU-ERP-embedded-payments.md
    ├── PRD-erp-embedded-payments.md
    └── opportunity-arisale-roadmap.md
```

## 🚀 Interactive Demos

### 1. MVP Demo ([index.html](./index.html))
Complete end-to-end payment flow simulation:
- **Phase 1**: Account discovery & awareness
- **Phase 2**: Account linking & authorization
- **Phase 3**: Terms & authorization
- **Phase 4**: Setup completion
- **Payment Flow**: Extract review → Pay with Interbank → SFTP processing → Results display

**Features**:
- Real-time SFTP processing simulation
- Individual payment status tracking
- Error handling and retry mechanisms
- Jobs-to-be-Done metrics tracking

**Access**: [/erp-embedded-payments](http://localhost:3000/erp-embedded-payments)

### 2. BPMN Process Flow ([bpmn-flow.html](./bpmn-flow.html))
Visual representation of the technical payment flow:
- User action sequence
- SFTP communication pattern
- Async processing states
- Error handling paths

## 📚 Key Documentation

### User Stories (5 HUs)

**[HU-001: Autorización de Cuenta ERP](../../docs/business/initiatives/2025-q4/ERP-partnerships/HU-ERP-embedded-payments.md#hu-001---autorización-de-cuenta-erp)**
- **Story Points**: 8
- **Priority**: High
- Initial authorization flow for embedded payments from ERP

**[HU-002: Procesamiento de Pago Masivo](../../docs/business/initiatives/2025-q4/ERP-partnerships/HU-ERP-embedded-payments.md#hu-002---procesamiento-de-pago-masivo)**
- **Story Points**: 13
- **Priority**: High
- Bulk payment execution from ERP extract (45 payments in <5 minutes)

**[HU-003: Visualización de Estados de Pago](../../docs/business/initiatives/2025-q4/ERP-partnerships/HU-ERP-embedded-payments.md#hu-003---visualización-de-estados-de-pago)**
- **Story Points**: 5
- **Priority**: Medium
- Individual transaction status display with filtering

**[HU-004: Recuperación de Pagos Fallidos](../../docs/business/initiatives/2025-q4/ERP-partnerships/HU-ERP-embedded-payments.md#hu-004---recuperación-de-pagos-fallidos)**
- **Story Points**: 8
- **Priority**: Medium
- Retry failed payments with data correction

**[HU-005: Configuración de Límites ERP](../../docs/business/initiatives/2025-q4/ERP-partnerships/HU-ERP-embedded-payments.md#hu-005---configuración-de-límites-erp)**
- **Story Points**: 5
- **Priority**: High
- Daily and per-transaction limit configuration

### Product Requirements

**[PRD: ERP Embedded Payments](../../docs/business/initiatives/2025-q4/ERP-partnerships/PRD-erp-embedded-payments.md)**
- Complete product requirements document
- Technical architecture using SFTP foundation
- Market analysis (ARI, Defontana)
- Success metrics and KPIs
- Q4 2025 - Q2 2026 roadmap

### Business Context

**[Opportunity & Roadmap](../../docs/business/initiatives/2025-q4/ERP-partnerships/opportunity-arisale-roadmap.md)**
- Market opportunity analysis
- ERP partner profiles
- Revenue projections
- Strategic positioning

## 🎨 Design System

All prototypes follow **Interbank Design System** guidelines:

### Color Palette
- **Primary Green**: `#05be50` (actions, success states)
- **Secondary Blue**: `#0039A6` (headers, corporate identity)
- **Gray Scale**: `#0F191E` (text) to `#F8F9FA` (background)

### Typography
- **Font Family**: Montserrat, sans-serif
- **Headers**: 600-700 weight
- **Body**: 400-500 weight

### Components
- Rounded corners: 8-16px
- Box shadows: Multi-level depth system
- Transitions: 0.15s (fast), 0.3s (normal), 0.5s (slow)

## 🔧 Technical Architecture

### SFTP Integration Flow
```
User in ERP → "Pay with Interbank"
  ↓
ERP generates payment file → Sends via SFTP
  ↓
User sees: "Instructions sent, results in ~10-20 min"
  ↓
Interbank PPA processes batch (background)
  ↓
Response file placed in SFTP folder
  ↓
ERP polls → Fetches → Displays individual results
```

### Key Technical Decisions
1. **Multi-Account Authorization**: ERPs can debit multiple client accounts (Risk Committee reviewed)
2. **Async Processing**: No real-time confirmation, 10-20 min processing window
3. **Individual Status**: Each payment in batch has separate status (Success/Failed/Details)
4. **SFTP Polling**: ERP monitors response folder every 2-3 minutes

## 📊 Success Metrics

### North Star Metric
**Monthly Payment Volume via ERP Integrations**: Target $50M+ by Q2 2026

### User-Centric KPIs
- **Payment Completion Time**: <30 seconds (vs 5-10 minutes manual)
- **Workflow Interruption**: 90% reduction
- **User Error Rate**: <0.5% (vs 3-5% manual)
- **User NPS**: >70 for embedded payment experience

### Partner Metrics
- **ARI User Activation**: 70% of eligible clients by Q2 2026
- **Defontana User Activation**: 60% of eligible clients by Q2 2026
- **Partner Satisfaction**: NPS >60 from ERP teams

## 🗓️ Roadmap

### Q4 2025: MVP Foundation
- **Week 1-4**: Legal & technical validation
- **Week 5-8**: Foundation setup (contracts, SFTP)
- **Week 9-12**: Integration & pilot (5-10 clients per ERP)

### Q1 2026: Scaling
- **Month 1**: Market expansion (200 active clients)
- **Month 2**: Feature enhancement (500 clients, $10M volume)
- **Month 3**: Strategic growth (1,000 clients, $25M volume)

### Q2 2026: Enterprise Scale
- 10+ active ERP integrations
- 2,000+ clients using embedded payments
- $50M+ monthly payment volume

## 🎯 Jobs-to-be-Done Framework

### Primary Job
**"Help me process mass payments without leaving my ERP workflow"**

**When**: Processing payment batches (payroll, suppliers) in ERP
**Want to**: Execute bulk payments directly from payment extracts
**So they can**: Complete payment cycles without manual file handling
**Without**: Downloading macros, switching to homebanking, managing multiple systems

### Current Pain Points
1. **Batch Processing Interruption**: Leave ERP for banking
2. **Macro Download Friction**: Generate → download → switch → upload → wait
3. **Bulk Status Uncertainty**: Which payments succeeded/failed?
4. **Context Loss**: Remember which batch, validate results manually
5. **Error Recovery**: Identify and retry failed payments manually

### Target Outcomes
- Complete payment cycles in <5 minutes (vs 15-20 min)
- Zero context switching
- Immediate individual payment status
- Automated reconciliation
- Simple error recovery

## 👥 Target Personas

### Persona 1: Finance Operations Manager (ARI)
- **Name**: Ana, manages AP for 200-employee distribution company
- **Current Job**: Weekly supplier batch (45 suppliers, S/127,000)
- **Pain Journey**: Review extract → validate → generate macro → download → homebanking → upload → wait → update status
- **Desired Outcome**: Process directly from ARI extract view
- **Success Metric**: <5 minutes vs 15-20 minutes

### Persona 2: Accounting Manager (Defontana)
- **Name**: Carlos, oversees finance for 500-employee manufacturing company
- **Current Job**: Bi-weekly payroll (500 employees) + monthly suppliers
- **Pain Journey**: Review payroll → validate → export → download → process → reconcile → update
- **Desired Outcome**: Execute from Defontana payment extracts
- **Success Metric**: Zero macro downloads, 90% time reduction

## 🔗 Related Resources

### Internal Documentation
- [Full HU Documentation](../../docs/business/initiatives/2025-q4/ERP-partnerships/HU-ERP-embedded-payments.md)
- [Complete PRD](../../docs/business/initiatives/2025-q4/ERP-partnerships/PRD-erp-embedded-payments.md)
- [Business Opportunity Analysis](../../docs/business/initiatives/2025-q4/ERP-partnerships/opportunity-arisale-roadmap.md)
- [VP Executive Presentation](../../docs/business/initiatives/2025-q4/ERP-partnerships/vp-one-slider-erp-embedded-payments.html)
- [Full Presentation Deck](../../docs/business/initiatives/2025-q4/ERP-partnerships/presentation-erp-partnerships.html)

### Main Mockups Index
- [Back to All Mockups](../index.html)
- [HU-008: Glosas World Class](../hu-008/)

### External References
- ARI ERP: [sale.somosari.com](https://sale.somosari.com)
- Defontana ERP: [www.defontana.com/pe](https://www.defontana.com/pe)

## 🚀 Getting Started

### View Demos Locally
```bash
cd mockups/erp-embedded-payments
open index.html
```

### Deploy to Vercel
Already configured in main `vercel.json`:
```json
{
  "rewrites": [
    { "source": "/erp-embedded-payments", "destination": "/erp-embedded-payments/index.html" },
    { "source": "/erp-embedded-payments/flow", "destination": "/erp-embedded-payments/bpmn-flow.html" }
  ]
}
```

Access at: [https://your-domain.vercel.app/erp-embedded-payments](https://mockups-interbank.vercel.app/erp-embedded-payments)

## 📞 Contact

**Product Manager**: Luis Huayaney
**Squad**: PPA (Plataforma de Pagos y Arquitectura)
**Initiative**: Q4 2025 Backlog #2 (Ecosistema Partners H2H)

---

**Last Updated**: October 2025
**Status**: 🟡 Q4 Execution (Pending Final Validations)
