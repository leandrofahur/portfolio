# Vercel Deployment Setup Guide

## Required GitHub Secrets

You need to add these secrets to your GitHub repository:

### 1. VERCEL_TOKEN
**How to get it:**
1. Go to [Vercel Dashboard](https://vercel.com/dashboard)
2. Click on your profile → **Settings**
3. Navigate to **Tokens** tab
4. Click **Create Token**
5. Give it a name like "GitHub Actions Deploy"
6. Set expiration (recommend: 90 days)
7. Copy the generated token

### 2. VERCEL_ORG_ID
**How to get it:**
1. Go to [Vercel Dashboard](https://vercel.com/dashboard)
2. Click on your profile → **Settings**
3. Navigate to **General** tab
4. Copy the **Team ID** (this is your org ID)

### 3. VERCEL_PROJECT_ID
**How to get it:**
1. Go to [Vercel Dashboard](https://vercel.com/dashboard)
2. Select your project
3. Go to **Settings** → **General**
4. Copy the **Project ID**

## Adding Secrets to GitHub

1. Go to your GitHub repository
2. Click **Settings** tab
3. Click **Secrets and variables** → **Actions**
4. Click **New repository secret**
5. Add each secret:
   - Name: `VERCEL_TOKEN`
   - Value: [paste your token]
   - Name: `VERCEL_ORG_ID`
   - Value: [paste your org ID]
   - Name: `VERCEL_PROJECT_ID`
   - Value: [paste your project ID]

## Security Best Practices

- ✅ **Never commit secrets to code**
- ✅ **Use repository secrets, not environment variables**
- ✅ **Rotate tokens regularly**
- ✅ **Set appropriate token expiration**
- ✅ **Use least privilege principle**

## Testing the Setup

After adding secrets, push to `dev` branch to test preview deployment:

```bash
git checkout -b dev
git push origin dev
```

Check the Actions tab to see if deployment succeeds. 