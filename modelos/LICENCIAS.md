# Modelos 3D: origen y licencias

| Archivo | Qué es | Autor | Origen | Licencia |
|---|---|---|---|---|
| `futbolista.glb` (malla y esqueleto) | Maniquí humano riggeado (rig estilo Unreal, 65 huesos), simplificado al 40 % (≈5,8 k triángulos) | Quaternius | "Universal Animation Library 2" [Standard], `UAL2_Standard.glb` — https://opengameart.org/sites/default/files/universal_animation_library_2standard.zip (página: https://opengameart.org/content/universal-animation-library-2) | CC0 1.0 (dominio público) |
| `futbolista.glb` (clips `Slide_Start`, `Slide_Loop`, `Hit_Knockback`, `Yes`) | Animaciones | Quaternius | El mismo zip de UAL 2 | CC0 1.0 |
| `futbolista.glb` (clips `Idle_Loop`, `Jog_Fwd_Loop`, `Sprint_Loop`, `Crouch_Idle_Loop`, `Crouch_Fwd_Loop`, `Dance_Loop`, `Jump_Start`) | Animaciones | Quaternius | "Universal Animation Library" [Standard], `AL_Standard.fbx` (versión Unreal, convertida a glTF con FBX2glTF) — https://opengameart.org/sites/default/files/universal_animation_librarystandard.zip (página: https://opengameart.org/content/universal-animation-library) | CC0 1.0 |

- Los dos zips traen `License.txt` con "CC0 1.0 Universal (CC0 1.0) Public Domain
  Dedication — Models by @Quaternius". En OpenGameArt los subió el mismo autor
  (usuario `quaternius`) con licencia CC0. Bajados sin cuenta el 2026-10-30.
- SHA-256 de los zips: UAL 1 `18ff1a72…7b85a3ac2`, UAL 2 `ec0e40d6…20391a9217`.
- CC0 no exige atribución; igual la dejamos acá.
- El GLB se arma con `scripts/modelos.mjs` (gltf-transform + meshoptimizer: dedos fuera,
  resample, cuantización y compresión meshopt). La camiseta, la cara y el pelo los pinta
  el juego (`src/actors/modelo/`): el GLB no trae texturas.

## Mixamo (modelo en uso)

- futbolista-mixamo.glb: personaje Remy y animaciones de Mixamo (Adobe). Uso libre en proyectos; no se redistribuyen los archivos sueltos.
- Clips: Offensive Soccer Idle, dribble trotando, fast run, soccer jog forward, soccer strafe
  (izq. y der.), soccer slide tackle, running fall over slide tackle, soccer trip, soccer 360
  spin y victory. Bajados por el usuario con su cuenta de Adobe (FBX, 30 fps, "in place").
- Los FBX originales viven en `juego/mixamo/`, que está en `.gitignore` y fuera de `public/`:
  no se suben ni se publican. El GLB se arma con `scripts/mixamo.mjs` (FBX2glTF +
  gltf-transform): sin pelo, pestañas, texturas ni UV; una primitiva por prenda; el pantalón
  ceñido debajo del short; simplificado a ~7,4 k triángulos, clips en el lugar, cuantizado y
  comprimido con meshopt.
- `futbolista.glb` (Quaternius, CC0) queda de repuesto: `?modelo=cc0` en la URL o
  `MODELO = QUATERNIUS` en `src/actors/modelo/config.ts`.

## Futbolista VS (respaldo: `?modelo=vs`)

- `futbolista-vs.glb` (malla): **malla propia**, hecha por código para este proyecto con
  `scripts/futbolista-vs.mjs` (tubos esculpidos alrededor de los huesos: camiseta con ribete,
  short, piel con cabeza, manos y músculos, botín con suela y tapones, ojos y siete peinados;
  ~5,5 k triángulos más un LOD simplificado de ~2,2 k con meshoptimizer). No sale de Remy ni
  de ningún modelo de terceros; no usa assets externos.
- `futbolista-vs.glb` (esqueleto y clips): los de Mixamo de `futbolista-mixamo.glb` (ver arriba),
  misma licencia de uso; tampoco se publican los FBX sueltos.
- Respaldo: `?modelo=mixamo` (Remy) o `?modelo=cc0` (Quaternius) en la URL.

## Futbolista alemán (modelo en uso)

- `futbolista-aleman.glb` (malla y texturas): **"German Soccer Player Rigged Character"**, comprado
  por el usuario en CGTrader. Autor: **constantin958**. Licencia **royalty free** de CGTrader
  (uso en productos propios, como este juego; no permite redistribuir los archivos del modelo
  tal cual ni venderlos como asset).
- En el juego va **convertido**: la malla horneada (sin la pelota), con UV propias de un atlas
  nuevo, y dos texturas derivadas (`detalle`: el sombreado del original como cociente, con
  escudo, tiras, número, estrellas y logos borrados; `zonas`: máscaras de color del club, piel,
  pelo y barba), en webp dentro del GLB. Los peinados son mallas propias hechas por código
  sobre su cráneo. Esqueleto y clips: los de Mixamo (ver arriba), con rig y pesos hechos acá.
- El GLB se arma con `scripts/futbolista-aleman.mjs` (FBX2glTF + gltf-transform + meshoptimizer
  + sharp, fuera del proyecto).
- **No se redistribuye crudo**: los archivos originales (FBX, OBJ, texturas PNG, `.rar`) viven en
  `juego/modelos-fuente/aleman/`, que está en `.gitignore` y fuera de `public/`; no se suben ni
  se publican. Solo se publica el GLB convertido.
- Respaldo: `?modelo=vs` (malla propia, versión 7), `?modelo=mixamo` (Remy) o `?modelo=cc0`.
