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
- Nada de Sega ni de Mixamo en esta versión.
