# SALIS AUTO - Backup & Recovery Procedures

**Version:** 1.0  
**Last Updated:** November 3, 2025  
**Review Frequency:** Monthly

---

## Backup Strategy

### Automated Backups

**Neon PostgreSQL (Primary Database):**
- **Frequency:** Continuous (point-in-time recovery)
- **Retention:** 7 days (free tier) / 30 days (paid tier)
- **Recovery Window:** Any point in the last N days
- **Storage:** Neon cloud storage (encrypted)
- **Verification:** Automated integrity checks

**Configuration:**
