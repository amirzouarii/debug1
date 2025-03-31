# debug1
Problème 1 : Une valeur d’état incorrecte
🛠 Erreur :
Dans React DevTools, vous voyez une variable d’état vide ("" au lieu d’un texte).

jsx
Copier
Modifier
const [title, setTitle] = useState(); // ❌ Mauvaise initialisation
✅ Solution :
Initialisez correctement l’état :

jsx
Copier
Modifier
const [title, setTitle] = useState(""); // ✅ Bon usage
🚨 Problème 2 : Propriété props manquante
🛠 Erreur :
Un composant ne reçoit pas la bonne prop, ou il affiche undefined :

jsx
Copier
Modifier
const MovieCard = ({ title }) => <h1>{title}</h1>;
// Appel incorrect dans un autre composant
<MovieCard /> // ❌ `title` est `undefined`
✅ Solution :
Ajoutez une valeur par défaut ou assurez-vous de passer correctement la prop :

jsx
Copier
Modifier
<MovieCard title="Inception" /> // ✅ Corrigé
Ou :

jsx
Copier
Modifier
const MovieCard = ({ title = "Titre par défaut" }) => <h1>{title}</h1>; // ✅ Défaut ajouté
🚨 Problème 3 : Mauvaise mise à jour d’état
🛠 Erreur :
Dans React DevTools, un état (state) ne se met pas à jour.
Exemple d'erreur :

jsx
Copier
Modifier
const handleClick = () => {
  count = count + 1; // ❌ Cela ne met pas à jour l’état
};
✅ Solution :
Toujours utiliser setState :

jsx
Copier
Modifier
const handleClick = () => {
  setCount(prevCount => prevCount + 1); // ✅ Bon usage
};
