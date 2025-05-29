# ION606's Chat-App

My second attempt at a chat app! Find the first one at https://github.com/Proto-Chat

## Roadmap

### current features

| area                            | highlights                                                                                                                                                                    |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **auth and sessions**           | secure registration / login / logout with bcrypt-hashed passwords and an express-session store backed by Redis                                                                |
| **data and storage**            | MongoDB connection helper with sensible indexes on messages, channels and servers ; MinIO object store + SVG fall-backs for avatars / banners / generic attachments           |
| **guild (server) system**       | create / list / edit / delete servers, including banner and icon upload, owner and admin checks, and “public / private / community” server types                              |
| **channels**                    | CRUD for text + voice channel records, per-role permission overwrites, validation helpers                                                                                     |
| **roles and permissions**       | full role CRUD with bit-mask permissions, default role protection, WebSocket broadcasts on change                                                                             |
| **member management**           | list members, self-endpoint, nickname / role edits, kick, ban and unban workflows                                                                                             |
| **direct messages and friends** | on-demand DM channel creation between two users ; friend-invite / accept / decline routes                                                                                     |
| **real-time layer**             | WebSocket endpoint with ping / subscribe and helpers to broadcast server-, channel- and friend-level events                                                                   |
| **frontend react spa**          | typed API client, React-Query hooks, and pages/components covering chat UI, role, member and channel management, file upload, dropdowns, modals, etc. (e.g., **ManageRoles**) |
| **dev-ops**                     | docker-compose stack (backend, frontend, Mongo, Redis, MinIO) and Dockerfiles for both services                                                                               |
| **utilities and validation**    | express-validator schemas for inputs, async error wrapper, default asset generator, permission helpers                                                                        |
| **Emojis**                      | embed into messages and when typed in chat                                                                                                                                    |
| **search and discovery**        | implement `/servers/discover` (currently returns 404) and global search for servers                                                                                           |

---

### Future Features

| category                            | components                                                                                                                                                                    |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **password and account management** | • user-initiated password change endpoint<br>• manager-level OTP reset flow for org members<br>• admin override resets and audit logging<br>• Send a OTP when a user signs up |
| **email workflows**                 | nodemailer integration for member invites and OTP/password-reset e-mails                                                                                                      |
| **moderation**                      | allow mods to kick/ban people, either via slash commands or context menu                                                                                                      |
| **Who reacted popup**               | create a popup to show who reacted with what. Allow mods to remove reactions                                                                                                  |
| **postgres migration**              | replace the Mongo-backed _users_ plugin with PostgreSQL and add Redis caching exclusively for frequent API-key permission checks                                              |
| **messages**                        | end-to-end message APIs (reactions, search), attachment lifecycle clean-up, typing indicators                                                                                 |
| **search**                          | global search for servers, users and messages                                                                                                                                 |
| **rate-limiting and security**      | per-route throttling, CSRF protection in cookies, fine-grained audit trail                                                                                                    |
| **frontend gaps**                   | UI for server discovery and global search, org dashboard, password-reset / invite screens, voice/video UI, push notifications, presence, full settings page                   |
| **accessibility and i18n**          | keyboard navigation, ARIA roles                                                                                                                                               |
| **ci/cd and testing**               | automated lint + type checks, Jest unit tests, Cypress end-to-end, container build pipeline                                                                                   |
| **observability and ops**           | structured logging, metrics, alerting, secrets management, optional CDN front for MinIO                                                                                       |

### Far in the Future Features

| category                   | components                                                                         |
| -------------------------- | ---------------------------------------------------------------------------------- |
| **voice / video channels** | Actual signaling and media-server logic—API currently only stores `"type":"voice"` |
| **mobile and PWA polish**  | Responsive layouts, offline caching, and PWA manifest updates                      |
