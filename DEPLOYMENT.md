# Quick Deployment Guide

## 🚀 Deploy to Vercel (Recommended)

### One-Command Deploy
```bash
cd mockups && npx vercel --prod
```

### Step-by-Step First Time Setup

1. **Navigate to mockups directory**:
   ```bash
   cd /Users/luishuayaney/Projects/Interbank/ibk-1/mockups
   ```

2. **Run Vercel deploy**:
   ```bash
   npx vercel
   ```

3. **Answer prompts**:
   ```
   ? Set up and deploy "~/Projects/Interbank/ibk-1/mockups"? [Y/n] Y
   ? Which scope? (Use arrow keys)
     > Your Vercel Account
   ? Link to existing project? [y/N] N
   ? What's your project's name? interbank-cashout-prototypes
   ? In which directory is your code located? ./
   ? Want to override the settings? [y/N] N
   ```

4. **Get your URL**:
   ```
   ✅ Preview: https://interbank-cashout-prototypes-xxxxx.vercel.app
   ```

5. **Deploy to production**:
   ```bash
   npx vercel --prod
   ```

   Production URL: `https://interbank-cashout-prototypes.vercel.app`

### Update Existing Deployment

```bash
cd mockups
npx vercel --prod
```

## 🌐 URL Structure

Once deployed:
- **Landing Page**: `https://your-project.vercel.app/`
- **HU-008 Demo**: `https://your-project.vercel.app/hu-008`
- **Future Demos**: `https://your-project.vercel.app/hu-XXX`

## 🧪 Test Locally Before Deploy

```bash
cd mockups
npx serve .
```

Open browser: `http://localhost:3000`

Test navigation:
- `/` → Landing page with all demos
- `/hu-008` → Glosas World Class demo
- Back button on demo should return to `/`

## 🔄 Continuous Deployment

### Option 1: Link to Git (Recommended for team)

1. **Initialize git in mockups** (if not already):
   ```bash
   cd mockups
   git init
   git add .
   git commit -m "Initial mockups setup"
   ```

2. **Push to GitHub**:
   ```bash
   gh repo create interbank-cashout-prototypes --private --source=. --remote=origin --push
   ```

3. **Link Vercel to GitHub**:
   - Go to vercel.com dashboard
   - Import project from GitHub
   - Select `interbank-cashout-prototypes`
   - Deploy

Now every push to `main` auto-deploys!

### Option 2: Manual Deploy (Current Setup)

Keep using `npx vercel --prod` for each update.

## ✅ Post-Deployment Checklist

- [ ] Landing page loads correctly
- [ ] All demo cards are visible
- [ ] HU-008 link navigates to demo
- [ ] Toggle switch works (Actual ↔ Nuevo)
- [ ] Back button returns to landing page
- [ ] Mobile responsive (test on phone)
- [ ] Stats section displays correctly

## 🐛 Troubleshooting

### Issue: 404 on /hu-008
**Solution**: Check `vercel.json` routes configuration. Redeploy with `vercel --prod --force`

### Issue: Styling broken
**Solution**: Verify all CSS is inline in HTML files (no external CSS files)

### Issue: Back button broken
**Solution**: Check link in [hu-008/index.html:360](hu-008/index.html#L360) points to `/` not `../`

### Issue: Wrong project name
**Solution**:
```bash
cd .vercel
cat project.json  # See current config
vercel --prod -m "project-name=new-name"
```

## 📞 Support

For Vercel issues: https://vercel.com/docs
For internal team questions: Contact Luis Huayaney
