# Interbank Cashout Prototypes - Demo Space

Interactive prototype demo space for Interbank B2B & B2E Cashout initiatives (Q4 2025 Roadmap).

## 🎯 Overview

This project hosts interactive prototypes for various cashout improvement initiatives, providing stakeholders with live demos and before/after comparisons.

## 📋 Current Demos

### HU-008: Glosas World Class
**Status**: ✅ LIVE
**URL**: `/hu-008`

Optimization of transaction descriptions in bank movements for clear identification. Interactive demo comparing current vs new format with Jobs-to-be-Done metrics.

**Key Features**:
- Toggle between "Actual" and "Nuevo" formats
- Real-time visual comparison
- Jobs-to-be-Done scoring (Identificar, Conciliar, Rastrear, Categorizar)
- +67% total improvement metrics
- World Class score: 8.75/10

**Context**: Based on HU-008 user story focusing on:
- Clear glosa/description with "Interbank" branding
- Operation number and relevant data
- Easy identification of origin, motive, and payment reference
- CCE character limit compliance (35 chars)
- Cross-channel consistency

### Upcoming Demos
- **HU-009**: Validación Titularidad Restrictiva BIE
- **HU-010**: Historial Extendido 12 Meses

## 🚀 Deployment

### Deploy to Vercel

1. **Install Vercel CLI** (if not installed):
   ```bash
   npm i -g vercel
   ```

2. **Deploy from mockups directory**:
   ```bash
   cd mockups
   vercel
   ```

3. **Follow prompts**:
   - Set up and deploy? `Y`
   - Which scope? (Select your Vercel account)
   - Link to existing project? `N`
   - Project name: `interbank-cashout-prototypes` (or custom)
   - Directory: `./` (current directory)
   - Override settings? `N`

4. **Production deployment**:
   ```bash
   vercel --prod
   ```

### Environment Configuration

No environment variables required - this is a static site.

### Custom Domain (Optional)

```bash
vercel domains add your-domain.com
```

## 📁 Project Structure

```
mockups/
├── index.html           # Main landing page with demo navigation
├── hu-008/
│   └── index.html      # HU-008 Glosas World Class demo
├── package.json         # Project metadata
├── vercel.json         # Vercel configuration
└── README.md           # This file
```

## 🛠️ Local Development

### Run locally with serve:
```bash
cd mockups
npx serve .
```

Visit `http://localhost:3000`

### Alternative with Python:
```bash
cd mockups
python3 -m http.server 3000
```

## 🎨 Design System

- **Primary Color**: `#00d170` (Interbank Green)
- **Secondary Color**: `#0066cc` (Interbank Blue)
- **Warning Color**: `#ff9800` (Orange)
- **Fonts**: System fonts stack (-apple-system, BlinkMacSystemFont, 'Segoe UI')
- **Mobile-first**: Fully responsive design

## 📊 Metrics & Analytics

Current impact metrics displayed:
- **JTBD Score Improvement**: +67%
- **World Class Score**: 8.75/10
- **Active Demos**: 1
- **Roadmap**: Q4 2025

## 🔗 Related Documentation

- User Story: `docs/business/initiatives/2025-q4/hu-mejora-glosa-movimientos-pagoproveedores/HU-008-mejora-glosa-descripcion-movimientos.md`
- Epic: Transaction Clarity
- Priority: Medium
- Story Points: 5

## 📝 Adding New Demos

1. Create new subdirectory: `mockups/hu-XXX/`
2. Add `index.html` in the subdirectory
3. Update `mockups/index.html` with new demo card
4. Add route in `vercel.json`:
   ```json
   {
     "src": "/hu-XXX",
     "dest": "/hu-XXX/index.html"
   }
   ```
5. Redeploy to Vercel

## 🤝 Contributing

For internal Interbank team use. To add or modify prototypes:
1. Create/modify HTML files
2. Test locally
3. Deploy to Vercel
4. Share URL with stakeholders

## 📄 License

UNLICENSED - Internal Interbank use only
