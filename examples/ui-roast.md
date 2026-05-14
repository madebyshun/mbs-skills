# Example — ui-roast

## Input

> Roast this UI. It's a DeFi dashboard — dark background, neon green accent, stats cards across the top, a big swap form in the center, and a table of recent transactions at the bottom. The font is Inter 14px throughout. Buttons are rounded with a neon green border on transparent background.

## Output

**1. Typography is flat and monotonous.**
Every element uses Inter 14px. There's no visual hierarchy — your $2.4M TVL stat reads the same as a table row timestamp. Fix: set a clear type scale. Stats cards need at least 28–32px for the number, 12px muted for the label.

**2. Neon green on dark is a contrast trap.**
Neon green (#00FF00 range) on pure black fails WCAG AA for small text. It looks loud but is actually hard to read. Shift to a slightly desaturated green (#22C55E or similar) and ensure 4.5:1 contrast ratio minimum.

**3. Ghost buttons are invisible.**
Transparent background + green border = low affordance. On a dark UI, users don't immediately read these as interactive. Use a filled primary button for the main swap action and reserve ghost style for secondary actions only.

**4. Stats cards have no information hierarchy.**
If all four stats look identical, the user's eye has nowhere to go. Decide what matters most (TVL? 24h volume?) and make it visually dominant.

**5. The transaction table is doing too much.**
Tables need clear column alignment, monospace for numbers, and subtle row separators. If it's using the same Inter 14px with neon green accents, it'll feel noisy.

---

**3 fixes to do today:**
1. Implement a type scale — at least 3 sizes with clear weight variation
2. Replace ghost buttons with a filled primary on the swap CTA
3. Reduce green usage to 1–2 key actions — let neutral tones carry the layout
