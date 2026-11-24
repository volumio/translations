# Italian (it): Volumio OS UI style guide

This guide covers the strings in `strings_it.json`: the device's settings pages, the
first-run wizard, the classic web UI, the MyVolumio account and plan pages, and the
system's toasts and dialogs. The translation tool sends it to the model with every
Italian batch. If it disagrees with the existing `strings_it.json`, follow the guide.

The voice, glossary and typography match the Nova UI's Italian guide
(`docs/i18n/style/it.md` in the Nova theme repository). Nova and the OS appear side by
side on the same device and quote each other's menu names, so one concept gets one
Italian word in both. If you change a term here, change it in Nova too.

## Voice

- Address the user as **tu**, never Lei, never impersonal infinitives
  (`Accendere il dispositivo` → `Accendi il dispositivo`). Write like the Italian UI of
  iOS or Android: friendly and direct, not bureaucratic, not marketing.
- Never write `si prega di…` or `per favore`. Use the imperative instead:
  `Riavvia il dispositivo e riprova`.
- Write what an Italian UI writer would write for that screen, not a word-for-word
  rendering of the English. If the literal version sounds translated, rephrase it.
- Keep it short. Italian runs about 20–30% longer than English. On buttons, menu
  entries, tabs and toggle labels, use the shortest natural form.
- Avoid `clicca`. The UI runs on phones, tablets, TVs and touchscreens, so use
  `tocca` only where the English says *tap*. Otherwise name the action
  (`Seleziona`, `Apri`) or the control (`usa il pulsante qui sotto`).

## Grammar by UI role

Each string has a role, given in its context line or implied by its key suffix.

- **Section titles and menu entries** (`MAIN_MENU.*`, `*_SETTINGS`, `*_OPTIONS`): noun
  phrases in sentence case. Capitalise the first word only, plus names:
  `Opzioni di riproduzione`, not `Opzioni Di Riproduzione`.
- **Setting labels** (a key with a sibling `*_DOC`): a noun phrase naming the setting
  (`Nome del player`, `Volume all'avvio`). A label that is a verb in English stays a
  verb (`Mostra impostazioni avanzate`).
- **`*_DOC` help texts** under a setting: one or two complete sentences, ending with a
  full stop. Say what the setting does and when to change it. These can be longer
  than the English, but must not repeat the label.
- **Buttons** (`SAVE`, `APPLY`, `ADD_*`, `REMOVE_*`, `*_BUTTON`): imperative tu-form
  verb, plus an object if needed: `Salva`, `Aggiungi disco`, `Riavvia`, `Riprova`. No
  articles unless the meaning needs them.
- **Toggle values and states** (`ON`, `OFF`, `ENABLED`, `DISABLED`): states are past
  participles agreeing with an unknown noun, so use the masculine singular
  (`Attivato`/`Disattivato`). Keep `On`/`Off` as they are, since every Italian
  device UI uses them.
- **Status and progress**: `… in corso…` or a nominal phrase:
  `Aggiornamento in corso…`, `Ricerca delle reti in corso…`.
- **Success toasts**: a past participle or a short sentence, with no "correttamente"
  or "con successo": `Impostazioni salvate`, `Disco di rete aggiunto`.
- **Errors**: say what happened and what to do, without blame:
  `Impossibile salvare le impostazioni. Riprova.` Never `Fallito`/`Fallita` on its own,
  `Errore fatale` or `Operazione abortita`. Turn `X failed` into `Impossibile <verbo> X`
  or `X non riuscito`.
- **Confirmation dialogs**: title as a question or noun phrase
  (`Ripristinare le impostazioni di fabbrica?`). The body says what will happen. The
  confirm button repeats the verb (`Ripristina`), not just `Ok`.
- **Screen-reader labels** (`ACCESSIBILITY.*`): a complete, explicit phrase. Length
  does not matter.

## Neutral wording for technical idioms

Never translate developer jargon literally. Use the meaning the user sees:

| English idea | Use | Never |
|---|---|---|
| kill / force quit | `Arresta`, `Chiudi`, `Interrompi` | uccidi |
| dead / unresponsive | `Non risponde`, `Non raggiungibile` | morto |
| crash | `Si è chiuso in modo imprevisto`, `Si è verificato un problema` | crash, crashato |
| hang / freeze | `Non risponde`, `Bloccato` | appeso |
| abort | `Annulla`, `Interrompi` | aborta, abortita |
| fatal / critical error | describe it, or `Errore grave` | errore fatale |
| failed | `Impossibile…`, `… non riuscito` | fallito (alone) |
| broken / faulty (about the device) | `Non riesce a…`, `Non raggiungibile` | rotto, guasto, difettoso |
| tweak / tweaking | `regolazione`, `impostazione` | tweak, settaggio |

Device problems are never presented as hardware faults. When a string describes
something going wrong with the player, frame it as a connection, network or setting
issue (`Il dispositivo non è raggiungibile in rete`), never as the unit being
defective.

## Glossary (one word per concept)

### Playback and library

| English | Italian |
|---|---|
| Track, Song | Brano (never traccia or canzone; `tracce` only for CD ripping) |
| Queue / Play queue | Coda |
| Browse | Sfoglia |
| Search | Cerca (button, tab), Ricerca (the activity) |
| Now playing | In riproduzione |
| Album art | Copertina |
| Playlist | Playlist (invariable) |
| Favorites | Preferiti |
| Library / My Music | Libreria / La mia musica |
| Sources | Sorgenti |
| Sources Visibility | Visibilità sorgenti (Nova quotes this name) |
| Music sources | Sorgenti musicali |
| Play (button) / Pause / Stop | Riproduci / Pausa / Stop |
| Play next | Riproduci dopo |
| Next / Previous track | Brano successivo / Brano precedente |
| Shuffle / Repeat / Repeat single | Riproduzione casuale / Ripeti / Ripeti brano |
| Volume / Mute | Volume / Disattiva audio (button), Muto (state) |
| Web radio | Web radio |
| Gapless | Senza interruzioni (gapless) on the first mention, then gapless |
| Crossfade | Dissolvenza incrociata |
| Volume normalization | Normalizzazione del volume |
| Playback options (menu) | Riproduzione |

### Audio output

Use the established audio terms and keep the industry acronyms in English.

| English | Italian |
|---|---|
| Audio output / Output device | Uscita audio / Dispositivo di uscita |
| DAC, I2S DAC, USB DAC | DAC, DAC I2S, DAC USB (always `I2S`, upper case) |
| Mixer type / Mixer control | Tipo di mixer / Controllo mixer |
| Mixer type values Hardware / Software / None | Hardware / Software / Nessuno (Nova quotes `Mixer: Nessuno`) |
| Resampling | Ricampionamento |
| Sample rate / Bit depth | Frequenza di campionamento / Profondità in bit |
| Bit-perfect, Hi-Res, DSP, ALSA | unchanged |
| Volume curve | Curva del volume |
| Startup volume | Volume all'avvio |
| Equalizer | Equalizzatore |

### Network and storage

| English | Italian |
|---|---|
| Network | Rete |
| Wired / Wireless network | Rete cablata / Rete wireless |
| Wi-Fi networks | Reti Wi-Fi |
| Network status | Stato della rete |
| Hotspot | Hotspot (invariable, masculine) |
| Static IP / DHCP | IP statico / DHCP |
| Network drive / NAS | Disco di rete / NAS (never `Hard Disk di rete`) |
| Network drives (page) | Dischi di rete |
| Share (SMB/NFS folder) | Cartella condivisa (never `Condividi`, which is the verb *to share*) |
| Mount / Mounted / Not mounted | Monta / Montato / Non montato (same words as Nova's network drives page) |
| USB drive | Unità USB |
| Install to disk | Installa su disco |
| CD ripping / Rip (button) | Copia dei CD / Copia (never `ripping`, never `Estrai`) |

### System and account

| English | Italian |
|---|---|
| Settings / System | Impostazioni / Sistema |
| Player name / Device name | Nome del player / Nome del dispositivo |
| Restart / Reboot | Riavvia |
| Shut down / Power off | Spegni |
| Update (noun / verb) | Aggiornamento / Aggiorna |
| Factory reset | Ripristino delle impostazioni di fabbrica (title), Ripristina (button) |
| Advanced settings | Impostazioni avanzate |
| Send logs / Debug | Invia i log / Debug |
| Plugin / Plugins | Plugin (invariable: `il plugin`, `i plugin`) |
| Install / Uninstall | Installa / Disinstalla |
| Edit | Modifica (never `Edita`) |
| Delete / Remove | Elimina (permanent) / Rimuovi (from a list or queue) |
| Enable / Disable | Attiva / Disattiva |
| Sign in / Sign out / Sign up | Accedi / Esci / Registrati |
| Account | Account |
| Subscription | Abbonamento |
| Plan (Free / Premium) | Piano Free / Piano Premium. Plan names stay English. Never `programma` or `abbonamento` for *plan*. |
| Free trial | Prova gratuita |
| Cancel subscription | Disdici l'abbonamento |
| Alarm / Sleep | Sveglia / Timer di spegnimento |
| Appearance | Aspetto |
| Wizard (first-run setup) | Configurazione iniziale |
| Yes / No / Ok | Sì / No / OK |
| Done / Cancel / Close / Back / Next / Skip | Fatto / Annulla / Chiudi / Indietro / Avanti / Salta |
| Learn more | Scopri di più |

Product, feature and protocol names stay in English: Volumio, MyVolumio, Nova,
TIDAL, TIDAL Connect, Qobuz, QOBUZ Connect, Spotify, Spotify Connect, Amazon Music,
AirPlay, Shairport, UPnP, DLNA, Roon, Bluetooth, Alexa, AI Infinity Playback, Premium,
Free, SMB, NFS, CIFS.

## Placeholders, fragments and agreement

- `__SIZE__` and any other `__NAME__`, `%s` or `{name}` token must appear exactly as
  written, once. Never translate it, change its letters or drop it.
- **Split sentences.** Some keys are halves of one sentence that the code joins
  around a value, for example `COMMON.ADD_QUEUE_TEXT_1` + *track title* +
  `COMMON.ADD_QUEUE_TEXT_2` ("Added *X* to queue"). Translate the pair together, keep
  the leading and trailing spaces exactly as the English has them, and choose
  wording that works whatever title is inserted. Use `Aggiunto ` / ` alla coda`,
  where `Aggiunto` agrees with the implied *brano*. Never move the whole sentence
  into one half and leave the other empty.
- Free-text names (devices, tracks, shares) have no known gender. Don't put an
  articled preposition in front of them: `su {name}`, not `sul {name}`.
- No plural logic exists. Phrase counts so that one form fits 1 and many
  (`Brani: 3`).

## Typography

- The accented capital E is `È`, never `E'`. `Sì` (yes) takes the accent.
- Use the straight apostrophe `'`. Quotation marks are “ ”.
- The ellipsis is the single character `…`, with no space before it.
- No full stop on buttons, labels, titles or single-phrase toasts. Use full stops
  on full sentences, including every `*_DOC`.
- Units and numbers keep the English form (`192 kHz`, `24 bit`). Don't add units
  the English doesn't have.
