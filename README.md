<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Main Courante PM</title>
  <style>
    body { font-family: Arial, sans-serif; background:#eef2f7; margin:0; padding:30px; }
    .container { max-width:1100px; margin:auto; background:white; padding:30px; border-radius:18px; box-shadow:0 10px 30px #0002; }
    h1 { margin-top:0; color:#1f2937; }
    h2 { color:#374151; border-bottom:1px solid #ddd; padding-bottom:8px; }
    label { font-weight:bold; display:block; margin-top:14px; }
    input, select, textarea { width:100%; padding:10px; margin-top:5px; border:1px solid #bbb; border-radius:8px; font-size:15px; }
    textarea { min-height:150px; }
    .grid { display:grid; grid-template-columns:1fr 1fr; gap:15px; }
    .bloc { background:#f9fafb; padding:18px; border-radius:14px; margin-top:20px; border:1px solid #ddd; }
    details { margin-top:20px; background:#f9fafb; padding:18px; border-radius:14px; border:1px solid #ddd; }
    summary { font-weight:bold; cursor:pointer; font-size:18px; }
    button { margin-top:25px; padding:12px 22px; border:0; border-radius:10px; background:#1f2937; color:white; font-weight:bold; cursor:pointer; }
    button:hover { background:#111827; }
  </style>
</head>

<body>
  <div class="container">
    <h1>Main Courante Police Municipale</h1>

    <div class="grid">
      <div>
        <label>Numéro de main courante</label>
        <input id="numero" readonly>
      </div>
      <div>
        <label>Date de création</label>
        <input id="dateCreation" readonly>
      </div>
    </div>

    <label>Nature de l’intervention</label>
    <select>
      <option>Tapage nocturne</option>
      <option>Différend de voisinage</option>
      <option>Ivresse publique manifeste</option>
      <option>Stationnement gênant</option>
      <option>Dépôt sauvage</option>
      <option>Chien dangereux / animal errant</option>
      <option>Assistance sapeurs-pompiers</option>
      <option>Rodéo urbain</option>
      <option>Violences intrafamiliales</option>
      <option>Sécurisation manifestation</option>
      <option>Renseignement</option>
      <option>Police administrative</option>
      <option>Autre</option>
    </select>

    <div class="bloc">
      <h2>Requérant</h2>
      <div class="grid">
        <input placeholder="Nom">
        <input placeholder="Prénom">
        <input placeholder="Adresse">
        <input placeholder="Téléphone">
        <input placeholder="Mail">
      </div>
    </div>

    <details>
      <summary>Victime — ouvrir si nécessaire</summary>
      <div class="grid">
        <input placeholder="Nom">
        <input placeholder="Prénom">
        <input placeholder="Adresse">
        <input placeholder="Téléphone">
        <input placeholder="Mail">
      </div>
    </details>

    <details>
      <summary>Auteur / mis en cause — ouvrir si nécessaire</summary>
      <div class="grid">
        <input placeholder="Nom">
        <input placeholder="Prénom">
        <input placeholder="Adresse">
        <input placeholder="Téléphone">
        <input placeholder="Mail">
      </div>
    </details>

    <label>Corps de la main courante</label>
    <textarea placeholder="Rédiger ici les faits, constatations, actions effectuées, chronologie, personnes rencontrées..."></textarea>

    <label>Suites à donner</label>
    <textarea placeholder="Transmission OPJ, information hiérarchie, surveillance, rappel réglementaire, procédure, classement..."></textarea>

    <button onclick="window.print()">Imprimer / Exporter en PDF</button>
  </div>

  <script>
    const now = new Date();
    document.getElementById("dateCreation").value =
      now.toLocaleDateString("fr-FR") + " " +
      now.toLocaleTimeString("fr-FR", { hour: "2-digit", minute: "2-digit" });

    const numero =
      "MC-" +
      now.getFullYear() +
      String(now.getMonth() + 1).padStart(2, "0") +
      String(now.getDate()).padStart(2, "0") +
      "-" +
      Math.floor(Math.random() * 9000 + 1000);

    document.getElementById("numero").value = numero;
  </script>
</body>
</html>
