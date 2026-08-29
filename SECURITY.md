# Security Policy

## Supported Versions

This project is under active development on the `testnet-implementation` branch.
Security fixes are applied to the `main` branch and the latest `testnet-implementation`
state. Older deployments are **not** supported with backported patches.

| Branch                | Supported |
| --------------------- | --------- |
| `main`                | ✅        |
| `testnet-implementation` | ✅     |
| any other / forks     | ❌        |

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues,
discussions, or pull requests.** Public issues are visible to anyone and would
disclose the flaw before a fix is available.

Instead, report privately using **GitHub private vulnerability reporting**:

1. Go to the repository's **Security** tab → **Report a vulnerability**.
2. Fill in the form with a description, affected component, and reproduction steps.
3. Submit. Only maintainers can see the report.

If private advisories are unavailable for any reason, you may also contact the
maintainers privately via the security contact listed in the repository
(`SECURITY` discussions are disabled; use the advisory flow above).

### Response SLA

We aim to acknowledge every private report within **3 business days** and to
provide a preliminary assessment within **7 business days**. A fix or
mitigation plan will be shared as soon as a root cause is confirmed. You will
be kept updated on progress until the issue is resolved and publicly disclosed
on a coordinated timeline (see below).

### Disclosure Timeline

- We request a **90-day** embargo from the date of your report before public
  disclosure, to allow time for a fix to ship.
- If a fix lands earlier, we are happy to coordinate earlier public disclosure
  with you and credit you (unless you prefer to remain anonymous).
- We will not pursue legal action against researchers who follow this policy.

## Scope

In scope for this security policy are the **five Soroban smart contracts** that
compose AutoMint and the frontend code that interacts with them:

1. **Token contract** (`contracts/token/`) — the `$AMT` token: minting,
   transfers, burns, allowances, and admin controls.
2. **Registry contract** (`contracts/registry/`) — usernames, point totals,
   leaderboard, and `add_points` accounting.
3. **Bot NFT contract** (`contracts/bot_nft/`) — bot ownership, tiers,
   minting, and transfers/escrow.
4. **Accrual contract** (`contracts/accrual/`) — point accrual math, claims,
   and threshold-based minting.
5. **Marketplace contract** (`contracts/marketplace/`) — P2P escrow listing,
   buying, and cancellation.

The associated frontend integration code under `frontend/src/lib/` and
`frontend/src/hooks/` that calls into these contracts is also in scope.

Out of scope:

- The underlying Stellar network, Soroban RPC, Horizon, or Freighter wallet.
- Third-party dependencies (report those upstream to their maintainers).
- Social engineering, phishing, or denial-of-service against maintainers.
- Issues requiring physical access to a maintainer's devices.

## Testnet Notice

> **All deployed contracts on the `testnet-implementation` branch are on
> Stellar Testnet.** Testnet accounts, tokens, and NFTs hold **no real-world
> value** — they use test lumens (`XLM`) obtained from Friendbot. Exploiting a
> vulnerability against a testnet deployment does not put real funds at risk.
>
> This does **not** exempt you from the safe-harbour commitments below, and we
> still ask that you report findings privately rather than exploiting or
> disclosing them publicly. Findings on a future mainnet deployment would be
> treated with the same process and higher urgency.

## Safe Harbour

We support responsible disclosure and will not pursue legal action against
researchers who:

- Report vulnerabilities through the private channel described above.
- Make a good-faith effort to avoid privacy violations, data destruction, or
  service interruption to others.
- Do not access, modify, or exfiltrate data that does not belong to them.
- Do not demand payment or post public proof-of-concept before coordinated
  disclosure.

Good-faith security research conducted under this policy is authorized. Any
legal complaint received about your research will be responded to with a
statement that your actions were conducted under this safe-harbour policy.

## Recognition

We are happy to acknowledge your contribution in release notes or a
SECURITY contributors list, provided you consent. If you prefer to remain
anonymous, we will respect that.
