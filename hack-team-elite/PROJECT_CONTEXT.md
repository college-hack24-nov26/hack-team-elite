# SAHARA Project Context

## Vision

SAHARA is planned as a student-first, privacy-conscious mental-wellbeing
platform. It should help people find approachable educational resources, reflect
on their wellbeing, explore self-guided coping tools, and find appropriate
human support. It is a college hackathon project, not a medical provider or a
replacement for professional care.

The current repository is an initial web-app scaffold. The product vision and
module list below describe proposed future scope; they are not claims about
features already implemented.

## Ten proposed mandatory modules

The repository does not currently define a canonical list of ten modules.
These proposed module boundaries provide a starting point for planning and
require the project owner's approval before implementation:

1. **Accounts and profiles** — user registration, sign-in, and basic profile
   preferences.
2. **Onboarding, consent, and privacy preferences** — explain the service's
   limits, collect necessary consent, and let users manage privacy choices.
3. **Wellbeing dashboard** — a clear, accessible starting point for the
   platform's resources and user-selected activities.
4. **Wellbeing check-ins and mood history** — optional user-entered reflections
   and trends, without diagnosing or interpreting them as a clinical result.
5. **Private journaling** — user-controlled written reflections with clear
   privacy, retention, and deletion behavior.
6. **Self-guided coping toolkit** — reviewed grounding, reflection, and
   wellbeing activities, presented as optional general resources.
7. **Mental-health learning library** — accessible educational material with
   review dates and credible sourcing.
8. **Non-diagnostic resource recommendations** — optional scikit-learn-assisted
   ranking of general resources, with transparent limits and a non-ML fallback;
   never a diagnosis, risk decision, or treatment recommendation.
9. **Moderated peer-support space** — if included, user interaction with
   reporting, moderation, and clear community boundaries.
10. **Human support and safety resources** — ways to find appropriate
    professional support and region-appropriate crisis resources, without
    implying that the platform is an emergency service.

## Target users

- **Primary intended users:** college and university students looking for
  general mental-wellbeing information and ways to find support.
- **Possible future users:** authorized content moderators or administrators,
  and professional-support providers if the project later includes a verified
  provider directory.

These are intended audiences, not implemented roles or verified service
relationships.

## Technology stack

Required project stack:

- Python 3.14.10
- FastAPI and Uvicorn
- PostgreSQL with SQLAlchemy
- Alembic for database migrations
- Jinja2 templates
- HTML, CSS, and vanilla JavaScript
- scikit-learn for strictly non-diagnostic resource ranking, if approved and
  supported by reviewed data

The current `backend/requirements.txt` lists FastAPI, Uvicorn, Jinja2,
SQLAlchemy, and `psycopg` (the PostgreSQL driver). It does not yet list Alembic
or scikit-learn.

## Medical safety requirements

- Present SAHARA as an informational and wellbeing-support platform, not a
  clinician, diagnostic service, or substitute for professional care.
- Do not claim to diagnose, prevent, or treat a medical condition.
- Do not implement AI or machine-learning diagnosis, clinical triage, or
  treatment recommendations. Recommendations, if implemented, must be limited
  to general resources and must not be presented as clinical conclusions.
- Make support and emergency limitations clear. Provide relevant, reviewed
  human/crisis-resource information when that module is implemented; do not
  imply that SAHARA monitors emergencies or can respond to them.
- Treat journals, check-ins, profiles, and support requests as sensitive
  information. Collect the minimum necessary; use explicit consent, appropriate
  access controls, secure transport/storage, and documented retention and
  deletion rules before collecting real user data.
- Review educational and coping content for accuracy, accessibility, and
  potential harm. Clearly identify its source and review status.
- If community features are built, provide moderation, reporting, and clear
  boundaries; do not promise that peer content is professional advice.
- Evaluate recommendation behavior for privacy, bias, and failure modes, and
  provide a useful non-ML path.

## Development rules

- There is one developer; favor small, verifiable increments and a manageable
  hackathon scope.
- Preserve Python 3.14.10 and the required stack. Use server-rendered Jinja2,
  HTML, CSS, and vanilla JavaScript; do not introduce Node.js, React, PHP,
  Supabase, or Lovable.
- Use SQLAlchemy for database access and Alembic migrations for schema changes;
  do not treat an unconfigured database as connected or use ad-hoc production
  schema changes.
- Keep secrets out of source, documentation, logs, and version control. Do not
  inspect, expose, or edit `.env` files as part of routine documentation work.
- Verify behavior with focused tests or runtime checks; document what was
  actually checked and distinguish it from unverified behavior.
- Do not overwrite or remove working files without explicit need. Keep
  documentation aligned with the actual implementation and mark planned work
  as planned.
- Avoid medical claims, diagnosis functionality, and unsupported claims about
  users, providers, or clinical effectiveness.
