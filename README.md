# Lumina AI

AI-powered learning platform for UK students.

## Deploy to Vercel

1. Push this repo to GitHub
2. Connect repo to Vercel
3. Add these environment variables in Vercel → Settings → Environment Variables:

| Variable | Where to get it |
|----------|----------------|
| `ANTHROPIC_API_KEY` | console.anthropic.com |
| `SUPABASE_URL` | Supabase → Settings → API → Project URL |
| `SUPABASE_ANON_KEY` | Supabase → Settings → API → anon public |
| `SUPABASE_SERVICE_KEY` | Supabase → Settings → API → service_role |
| `SITE_URL` | Your Vercel URL e.g. https://lumina-ai.vercel.app |
| `RESEND_API_KEY` | resend.com → API Keys |
| `ADMIN_SECRET_KEY` | Any password you choose |
| `STRIPE_SECRET_KEY` | stripe.com → Developers → API Keys |
| `STRIPE_PRICE_STUDENT` | Stripe → Products → Student Plan price ID |
| `STRIPE_PRICE_HOMESCHOOL` | Stripe → Products → Homeschool Plan price ID |
| `STRIPE_WEBHOOK_SECRET` | Stripe → Webhooks → signing secret |

4. Run `supabase-schema.sql` in your Supabase SQL Editor
5. Deploy — Vercel will auto-build on every push

## Stripe Webhook
Point your Stripe webhook to: `https://your-site.vercel.app/api/webhook`

Events needed:
- checkout.session.completed
- invoice.payment_succeeded
- invoice.payment_failed
- customer.subscription.deleted
