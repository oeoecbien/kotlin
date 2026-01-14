# Cours de Révision - Kotlin et Développement Android
## Guide concis pour QCM

---

## 1. BASES DE KOTLIN

### 1.1 Opérateurs et Types de Données

**Types de base :**
- `Int` : nombre entier (ex: `val age: Int = 25`)
- `Long` : grand entier (ex: `val bigNumber: Long = 1000000L`)
- `Float` : décimal simple précision (ex: `val pi: Float = 3.14f`)
- `Double` : décimal double précision (ex: `val price: Double = 19.99`)
- `Char` : caractère unique (ex: `val letter: Char = 'A'`)
- `String` : chaîne de caractères (ex: `val name: String = "Alice"`)
- `Boolean` : vrai/faux (ex: `val isActive: Boolean = true`)

**Opérateurs arithmétiques :**
- `+` : addition (ex: `val sum = 5 + 3` → 8)
- `-` : soustraction (ex: `val diff = 10 - 4` → 6)
- `*` : multiplication (ex: `val product = 3 * 4` → 12)
- `/` : division (ex: `val quotient = 15 / 3` → 5)
- `%` : modulo (ex: `val remainder = 10 % 3` → 1)

**Opérateurs de comparaison :**
- `==` : égalité (ex: `if (a == b)`)
- `!=` : inégalité (ex: `if (a != b)`)
- `<`, `>`, `<=`, `>=` : comparaisons (ex: `if (age >= 18)`)

**Opérateurs logiques :**
- `&&` : ET (ex: `if (age > 18 && hasLicense)`)
- `||` : OU (ex: `if (isStudent || isTeacher)`)
- `!` : NON (ex: `if (!isFinished)`)

**Opérateurs d'assignation :**
- `=` : assignation (ex: `var x = 5`)
- `+=` : addition puis assignation (ex: `x += 3` équivaut à `x = x + 3`)
- `-=`, `*=`, `/=` : similaires

**Ranges :**
- `..` : range inclusif (ex: `for (i in 1..5)` → 1, 2, 3, 4, 5)
- `until` : range exclusif fin (ex: `for (i in 1 until 5` → 1, 2, 3, 4)
- `downTo` : range décroissant (ex: `for (i in 5 downTo 1` → 5, 4, 3, 2, 1)
- `step` : pas (ex: `for (i in 1..10 step 2` → 1, 3, 5, 7, 9)

**Nullabilité :**
- `?` : type nullable (ex: `val name: String? = null`)
- `!!` : assertion non-null, peut crasher (ex: `val length = name!!.length`)
- `?.` : safe call, retourne null si null (ex: `val length = name?.length`)
- `?:` : Elvis operator, valeur par défaut si null (ex: `val x = y ?: 0`)
- Exemple complet : `val result = user?.name?.length ?: -1`

**Collections :**
- `List<T>` : liste immuable ordonnée (ex: `val numbers = listOf(1, 2, 3)`)
- `MutableList<T>` : liste modifiable (ex: `val list = mutableListOf(1, 2, 3)`)
- `Set<T>` : ensemble unique (ex: `val unique = setOf(1, 2, 2, 3)` → {1, 2, 3})
- `Map<K, V>` : dictionnaire (ex: `val map = mapOf("key" to "value")`)
- `arrayOf()` : tableau (ex: `val arr = arrayOf(1, 2, 3)`)

### 1.2 Fonctions

**Déclaration classique :**
```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}
```

**Fonction expression (une ligne) :**
```kotlin
fun add(a: Int, b: Int) = a + b
```

**Paramètres par défaut :**
```kotlin
fun greet(name: String = "World") = "Hello, $name"
// greet() → "Hello, World"
// greet("Alice") → "Hello, Alice"
```

**Paramètres nommés :**
```kotlin
fun createUser(name: String, age: Int, city: String) { }
// createUser(name = "Bob", age = 25, city = "Paris")
```

**Vararg (nombre variable d'arguments) :**
```kotlin
fun sum(vararg numbers: Int): Int {
    return numbers.sum()
}
// sum(1, 2, 3, 4) → 10
```

**Fonction d'extension :**
```kotlin
fun String.capitalizeFirst(): String {
    return this[0].uppercase() + this.substring(1)
}
// "hello".capitalizeFirst() → "Hello"
```

**Fonctions d'ordre supérieur :**
- `forEach` : parcourt chaque élément (ex: `list.forEach { println(it) }`)
- `map` : transforme chaque élément (ex: `list.map { it * 2 }`)
- `filter` : filtre les éléments (ex: `list.filter { it > 5 }`)
- `reduce` : réduit à une valeur (ex: `list.reduce { acc, n -> acc + n }`)
- `fold` : réduit avec valeur initiale (ex: `list.fold(0) { acc, n -> acc + n }`)

**Lambda :**
```kotlin
val double = { x: Int -> x * 2 }
// double(5) → 10

val numbers = listOf(1, 2, 3)
numbers.map { it * 2 } // it = élément courant
```

### 1.3 Classes et Objets

**Classe simple :**
```kotlin
class Personne(val nom: String, var age: Int) {
    fun parler() = "Bonjour, je suis $nom"
}
// val p = Personne("Alice", 25)
```

**Bloc init (constructeur) :**
```kotlin
class Personne(val nom: String) {
    init {
        println("Personne créée: $nom")
    }
}
```

**Propriétés :**
- `val` : immuable, read-only (ex: `val name: String`)
- `var` : mutable (ex: `var age: Int`)

**Getter/Setter personnalisés :**
```kotlin
class Rectangle(val width: Int, val height: Int) {
    val area: Int
        get() = width * height
}
```

**Visibilité :**
- `public` : par défaut, accessible partout
- `private` : accessible uniquement dans la classe (ex: `private val secret: String`)
- `protected` : accessible dans la classe et sous-classes
- `internal` : accessible dans le même module

**Héritage :**
```kotlin
open class Animal(val nom: String) {
    open fun faireBruit() = "Bruit"
}

class Chien(nom: String) : Animal(nom) {
    override fun faireBruit() = "Wouf!"
}
```

**Data class :**
```kotlin
data class User(val id: Int, val name: String)
// Génère automatiquement : equals(), hashCode(), toString(), copy()
val user1 = User(1, "Alice")
val user2 = user1.copy(name = "Bob") // copie avec modification
```

**Object (singleton) :**
```kotlin
object Database {
    fun connect() { }
}
// Database.connect() - une seule instance
```

**Companion Object :**
```kotlin
class MyClass {
    companion object {
        const val CONSTANT = "Valeur"
    }
}
// MyClass.CONSTANT
```

**Enum :**
```kotlin
enum class Direction { NORD, SUD, EST, OUEST }
// val dir = Direction.NORD
```

---

## 2. PREMIÈRE APPLICATION ANDROID

### 2.1 Structure d'un Projet Android

**Fichiers essentiels :**
- `AndroidManifest.xml` : configuration de l'app (permissions, activités)
- `MainActivity.kt` : point d'entrée de l'application
- `build.gradle.kts` : dépendances et configuration du projet
- `res/` : ressources (drawable, layout, values)

**Activity :**
```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            MonApp()
        }
    }
}
```

**Cycle de vie Android :**
- `onCreate()` : création de l'Activity (ex: initialisation)
- `onStart()` : Activity visible mais pas au premier plan
- `onResume()` : Activity active et interactive
- `onPause()` : Activity en pause (ex: autre app au premier plan)
- `onStop()` : Activity non visible
- `onDestroy()` : Activity détruite

**Ordre d'appel :**
```
onCreate() → onStart() → onResume() → [utilisateur] → onPause() → onStop() → onDestroy()
```

### 2.2 Jetpack Compose - Bases

**Composable :**
```kotlin
@Composable
fun MonComposable() {
    Text("Hello World")
}
```

**Layouts :**
- `Column` : disposition verticale (ex: `Column { Text("A"); Text("B") }`)
- `Row` : disposition horizontale (ex: `Row { Text("A"); Text("B") }`)
- `Box` : superposition (ex: `Box { Image(); Text() }`)
- `Spacer` : espacement (ex: `Spacer(modifier = Modifier.height(16.dp))`)

**Modifiers essentiels :**
- `Modifier.fillMaxSize()` : prend toute la taille disponible
- `Modifier.fillMaxWidth()` : prend toute la largeur
- `Modifier.fillMaxHeight()` : prend toute la hauteur
- `Modifier.padding(16.dp)` : espacement interne
- `Modifier.size(100.dp)` : taille fixe
- `Modifier.wrapContentSize()` : taille selon le contenu
- `Modifier.height(50.dp)` : hauteur fixe
- `Modifier.width(100.dp)` : largeur fixe

**Composables Material 3 :**
- `Button` : bouton (ex: `Button(onClick = { }) { Text("Cliquer") }`)
- `Text` : texte (ex: `Text("Hello")`)
- `TextField` : champ de saisie (ex: `TextField(value = text, onValueChange = { text = it })`)
- `Image` : image (ex: `Image(painter = painterResource(R.drawable.icon), contentDescription = "Icon")`)
- `Card` : carte (ex: `Card { Text("Contenu") }`)
- `Scaffold` : structure de base avec AppBar
- `TopAppBar` : barre d'application en haut

**Exemple complet :**
```kotlin
@Composable
fun MonEcran() {
    Column(
        modifier = Modifier.fillMaxSize(),
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Text("Titre")
        Spacer(modifier = Modifier.height(16.dp))
        Button(onClick = { }) {
            Text("Action")
        }
    }
}
```

---

## 3. GESTION D'ÉTAT

### 3.1 État dans Compose

**remember et mutableStateOf :**
```kotlin
var compteur by remember { mutableStateOf(0) }
// compteur = 0 initialement
// Modifier : compteur = 5 → déclenche recomposition
```

**Exemple complet :**
```kotlin
@Composable
fun Compteur() {
    var count by remember { mutableStateOf(0) }
    Button(onClick = { count++ }) {
        Text("Compteur: $count")
    }
}
```

**rememberSaveable :**
- Persiste l'état lors des changements de configuration (rotation)
```kotlin
var state by rememberSaveable { mutableStateOf(0) }
// Survit à la rotation d'écran
```

**Recomposition :**
- Se déclenche automatiquement quand l'état change
- Seules les fonctions `@Composable` sont recomposées
- Exemple : `var x = 5` → `x = 10` → UI se met à jour automatiquement

### 3.2 Gestion d'État Avancée

**États multiples :**
```kotlin
var step by remember { mutableStateOf(1) }
var count by remember { mutableStateOf(0) }
var isActive by remember { mutableStateOf(false) }
```

**États conditionnels avec when :**
```kotlin
when (state) {
    1 -> AfficherEtape1()
    2 -> AfficherEtape2()
    3 -> AfficherEtape3()
    else -> AfficherFin()
}
```

**Saisie utilisateur :**
```kotlin
var text by remember { mutableStateOf("") }
TextField(
    value = text,
    onValueChange = { text = it },
    label = { Text("Nom") }
)
// Chaque frappe met à jour text et déclenche recomposition
```

**Exemple multi-états :**
```kotlin
@Composable
fun LemonadeApp() {
    var step by remember { mutableStateOf(1) }
    var squeezeCount by remember { mutableStateOf(0) }
    
    when (step) {
        1 -> Button(onClick = { step = 2 }) { Text("Sélectionner") }
        2 -> Button(onClick = { 
            squeezeCount++
            if (squeezeCount >= 3) step = 3
        }) { Text("Presser: $squeezeCount") }
        3 -> Button(onClick = { step = 4 }) { Text("Boire") }
        4 -> Button(onClick = { step = 1; squeezeCount = 0 }) { Text("Redémarrer") }
    }
}
```

---

## 4. LISTES ET DONNÉES

### 4.1 Classes de Données

**Data class :**
```kotlin
data class Affirmation(
    val id: Int,
    val text: String,
    val image: Int
)
```

**Avantages automatiques :**
- `equals()` : comparaison (ex: `aff1 == aff2`)
- `hashCode()` : hash pour collections
- `toString()` : représentation texte (ex: `println(aff)` → "Affirmation(id=1, text=...)")
- `copy()` : copie avec modifications (ex: `val new = old.copy(text = "Nouveau")`)

**Destructuring :**
```kotlin
val (id, text, image) = affirmation
// id = affirmation.id, text = affirmation.text, etc.
```

**Exemple d'utilisation :**
```kotlin
val affirmation = Affirmation(1, "Vous êtes génial", R.drawable.image1)
val modified = affirmation.copy(text = "Vous êtes excellent")
```

### 4.2 Listes dans Compose

**LazyColumn (liste verticale) :**
```kotlin
val items = listOf("Item 1", "Item 2", "Item 3")
LazyColumn {
    items(items) { item ->
        Text(item)
    }
}
```

**LazyRow (liste horizontale) :**
```kotlin
LazyRow {
    items(items) { item ->
        Card { Text(item) }
    }
}
```

**LazyVerticalGrid (grille) :**
```kotlin
LazyVerticalGrid(
    columns = GridCells.Fixed(2) // 2 colonnes
) {
    items(items) { item ->
        ItemCard(item)
    }
}
```

**Avantages du chargement paresseux :**
- Ne charge que les éléments visibles à l'écran
- Performance optimale pour grandes listes (1000+ éléments)
- Défilement fluide

**Exemple complet :**
```kotlin
@Composable
fun AffirmationsList(affirmations: List<Affirmation>) {
    LazyColumn {
        items(affirmations) { affirmation ->
            Card(
                modifier = Modifier.fillMaxWidth()
            ) {
                Column {
                    Image(painterResource(affirmation.image), null)
                    Text(affirmation.text)
                }
            }
        }
    }
}
```

### 4.3 Composants Material

**Card simple :**
```kotlin
Card(
    modifier = Modifier.fillMaxWidth(),
    elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
) {
    Text("Contenu de la carte")
}
```

**Card extensible :**
```kotlin
var expanded by remember { mutableStateOf(false) }
Card(
    onClick = { expanded = !expanded }
) {
    Column(
        modifier = Modifier.animateContentSize() // Animation fluide
    ) {
        Text("Titre")
        if (expanded) {
            Text("Contenu détaillé visible")
        }
    }
}
```

**Exemple avec animation :**
```kotlin
@Composable
fun ExpandableCard() {
    var expanded by remember { mutableStateOf(false) }
    Card(
        onClick = { expanded = !expanded }
    ) {
        Column(
            modifier = Modifier.animateContentSize()
        ) {
            Text("Cliquez pour ${if (expanded) "réduire" else "étendre"}")
            if (expanded) {
                Text("Contenu supplémentaire")
            }
        }
    }
}
```

---

## 5. ARCHITECTURE ANDROID

### 5.1 Architecture Components

**ViewModel :**
- Survit aux changements de configuration (rotation d'écran)
- Gère la logique métier (séparation UI / Logique)
- Persiste les données pendant le cycle de vie

```kotlin
class MyViewModel : ViewModel() {
    private val _uiState = MutableStateFlow(UiState())
    val uiState: StateFlow<UiState> = _uiState.asStateFlow()
    
    fun updateState() {
        _uiState.update { currentState ->
            currentState.copy(score = currentState.score + 1)
        }
    }
}
```

**Utilisation dans Compose :**
```kotlin
@Composable
fun MyScreen(viewModel: MyViewModel = viewModel()) {
    val uiState by viewModel.uiState.collectAsState()
    Text("Score: ${uiState.score}")
    Button(onClick = { viewModel.updateState() }) {
        Text("Incrémenter")
    }
}
```

**Exemple complet :**
```kotlin
// ViewModel
class GameViewModel : ViewModel() {
    private val _score = MutableStateFlow(0)
    val score: StateFlow<Int> = _score.asStateFlow()
    
    fun incrementScore() {
        _score.update { it + 1 }
    }
}

// Composable
@Composable
fun GameScreen() {
    val viewModel: GameViewModel = viewModel()
    val score by viewModel.score.collectAsState()
    
    Column {
        Text("Score: $score")
        Button(onClick = { viewModel.incrementScore() }) {
            Text("+1")
        }
    }
}
```

### 5.2 StateFlow et Flow

**StateFlow :**
- État observable et réactif
- Émet la valeur actuelle aux nouveaux collecteurs
- Thread-safe (sécurisé pour les threads)

**MutableStateFlow :**
```kotlin
private val _state = MutableStateFlow(initialValue)
val state: StateFlow<Type> = _state.asStateFlow()
// _state : privé, modifiable
// state : public, lecture seule
```

**Collecter dans Compose :**
```kotlin
val state by viewModel.state.collectAsState()
// state se met à jour automatiquement quand _state change
```

**update() :**
```kotlin
_state.update { currentState ->
    currentState.copy(
        field1 = newValue1,
        field2 = newValue2
    )
}
// Mise à jour thread-safe et immuable
```

**Exemple avec data class :**
```kotlin
data class GameUiState(
    val score: Int = 0,
    val currentWord: String = "",
    val isGameOver: Boolean = false
)

class GameViewModel : ViewModel() {
    private val _uiState = MutableStateFlow(GameUiState())
    val uiState: StateFlow<GameUiState> = _uiState.asStateFlow()
    
    fun checkAnswer(answer: String) {
        _uiState.update { currentState ->
            if (answer == currentState.currentWord) {
                currentState.copy(score = currentState.score + 10)
            } else {
                currentState.copy(isGameOver = true)
            }
        }
    }
}
```

### 5.3 Cycle de Vie et Persistance

**Logcat :**
- `Log.d("TAG", "message")` : debug (ex: `Log.d("MainActivity", "onCreate appelé")`)
- `Log.e("TAG", "message")` : erreur (ex: `Log.e("API", "Erreur réseau")`)
- `Log.i("TAG", "message")` : info (ex: `Log.i("User", "Connexion réussie")`)
- `Log.w("TAG", "message")` : warning
- `Log.v("TAG", "message")` : verbose

**Intents :**
```kotlin
// Partager du texte
val intent = Intent(Intent.ACTION_SEND).apply {
    type = "text/plain"
    putExtra(Intent.EXTRA_TEXT, "Message à partager")
}
startActivity(Intent.createChooser(intent, "Partager via"))
```

**rememberSaveable :**
- Sauvegarde automatique dans Bundle
- Survit aux rotations d'écran
```kotlin
var counter by rememberSaveable { mutableStateOf(0) }
// Si rotation : counter garde sa valeur
```

**Exemple :**
```kotlin
@Composable
fun MyScreen() {
    // Survit à la rotation
    var count by rememberSaveable { mutableStateOf(0) }
    
    // Ne survit PAS à la rotation
    var temp by remember { mutableStateOf("") }
}
```

---

## 6. COROUTINES KOTLIN

### 6.1 Concepts de Base

**Fonction suspendue :**
```kotlin
suspend fun maFonction() {
    delay(1000) // pause de 1 seconde (non-bloquant)
    println("Terminé")
}
// Ne peut être appelée que dans une coroutine
```

**CoroutineScope :**
```kotlin
coroutineScope {
    launch { task1() }
    launch { task2() }
}
// Attend que toutes les tâches se terminent
```

**launch :**
- Lance une coroutine
- Ne retourne pas de valeur
- Fire-and-forget (lance et oublie)
```kotlin
viewModelScope.launch {
    delay(1000)
    println("Après 1 seconde")
}
```

**async / await :**
```kotlin
val result = async { calculLong() } // Lance en parallèle
val valeur = result.await() // Attend le résultat
```

**Exemple :**
```kotlin
viewModelScope.launch {
    val task1 = async { fetchData1() }
    val task2 = async { fetchData2() }
    val results = listOf(task1.await(), task2.await())
}
```

### 6.2 Utilisation dans Compose

**LaunchedEffect :**
```kotlin
LaunchedEffect(key1 = dependency) {
    // Code suspendu exécuté une fois au démarrage
    // et re-exécuté si dependency change
    maFonctionSuspendue()
}
```

**Exemple avec compteur :**
```kotlin
@Composable
fun RaceTracker() {
    var progress by remember { mutableStateOf(0) }
    
    LaunchedEffect(Unit) { // Unit = exécute une seule fois
        while (progress < 100) {
            delay(500) // Attendre 500ms
            progress += 10
        }
    }
    
    LinearProgressIndicator(progress = progress / 100f)
}
```

**Exemple avec dépendance :**
```kotlin
@Composable
fun Timer(isActive: Boolean) {
    var time by remember { mutableStateOf(0) }
    
    LaunchedEffect(isActive) { // Re-exécute si isActive change
        if (isActive) {
            while (true) {
                delay(1000)
                time++
            }
        }
    }
    
    Text("Temps: $time")
}
```

**Dispatchers :**
- `Dispatchers.Main` : UI thread (ex: `withContext(Dispatchers.Main) { updateUI() }`)
- `Dispatchers.IO` : opérations I/O (ex: `withContext(Dispatchers.IO) { readFile() }`)
- `Dispatchers.Default` : calculs CPU (ex: `withContext(Dispatchers.Default) { heavyCalculation() }`)

### 6.3 Exécution Concurrente

**Parallélisme :**
```kotlin
coroutineScope {
    val task1 = async { operation1() } // Lance en parallèle
    val task2 = async { operation2() } // Lance en parallèle
    val results = listOf(task1.await(), task2.await()) // Attend les deux
}
```

**Exemple concret :**
```kotlin
suspend fun fetchUserData(): UserData {
    return coroutineScope {
        val user = async { fetchUser() }
        val posts = async { fetchPosts() }
        val friends = async { fetchFriends() }
        
        UserData(
            user = user.await(),
            posts = posts.await(),
            friends = friends.await()
        )
    }
}
// Les 3 appels se font en parallèle, pas séquentiellement
```

**Annulation :**
- Les coroutines sont annulées automatiquement si le scope est annulé
- Utiliser `isActive` pour vérifier l'état
```kotlin
suspend fun longTask() {
    while (isActive) { // Vérifie si toujours actif
        delay(100)
        doWork()
    }
}
```

---

## 7. ACCÈS INTERNET ET RÉSEAU

### 7.1 Retrofit

**Interface de service :**
```kotlin
interface ApiService {
    @GET("photos")
    suspend fun getPhotos(): List<MarsPhoto>
    
    @GET("users/{id}")
    suspend fun getUser(@Path("id") userId: Int): User
    
    @POST("users")
    suspend fun createUser(@Body user: User): User
}
```

**Configuration Retrofit :**
```kotlin
private val retrofit = Retrofit.Builder()
    .baseUrl("https://api.example.com/")
    .addConverterFactory(Json.asConverterFactory("application/json".toMediaType()))
    .build()

val apiService: ApiService = retrofit.create(ApiService::class.java)
```

**Appel dans ViewModel :**
```kotlin
class MarsViewModel : ViewModel() {
    private val _uiState = MutableStateFlow<UiState>(UiState.Loading)
    val uiState: StateFlow<UiState> = _uiState.asStateFlow()
    
    init {
        getMarsPhotos()
    }
    
    private fun getMarsPhotos() {
        viewModelScope.launch {
            try {
                val photos = MarsApi.retrofitService.getPhotos()
                _uiState.value = UiState.Success(photos)
            } catch (e: Exception) {
                _uiState.value = UiState.Error(e.message ?: "Erreur inconnue")
            }
        }
    }
}
```

**Exemple complet :**
```kotlin
// Service
interface MarsApiService {
    @GET("photos")
    suspend fun getPhotos(): List<MarsPhoto>
}

// ViewModel
class MarsViewModel : ViewModel() {
    private val _uiState = MutableStateFlow<UiState>(UiState.Loading)
    val uiState = _uiState.asStateFlow()
    
    fun loadPhotos() {
        viewModelScope.launch {
            _uiState.value = UiState.Loading
            try {
                val photos = MarsApi.retrofitService.getPhotos()
                _uiState.value = UiState.Success(photos)
            } catch (e: IOException) {
                _uiState.value = UiState.Error("Erreur réseau")
            }
        }
    }
}
```

### 7.2 Sérialisation JSON

**kotlinx.serialization :**
```kotlin
@Serializable
data class MarsPhoto(
    val id: String,
    @SerialName("img_src") val imageUrl: String
)
```

**Annotations :**
- `@Serializable` : classe sérialisable (ex: `@Serializable data class User(...)`)
- `@SerialName("nom_json")` : nom différent dans JSON (ex: `@SerialName("user_name") val name: String`)

**Exemple :**
```kotlin
// JSON: {"id": "1", "img_src": "https://..."}
@Serializable
data class MarsPhoto(
    val id: String,
    @SerialName("img_src") val imageUrl: String
)
// Kotlin: MarsPhoto(id = "1", imageUrl = "https://...")
```

### 7.3 Chargement d'Images

**Coil avec AsyncImage :**
```kotlin
AsyncImage(
    model = imageUrl,
    contentDescription = "Description de l'image",
    modifier = Modifier.size(200.dp)
)
```

**Gestion d'erreur et placeholder :**
```kotlin
AsyncImage(
    model = imageUrl,
    contentDescription = null,
    error = painterResource(R.drawable.error_image),
    placeholder = painterResource(R.drawable.loading_image),
    modifier = Modifier.fillMaxWidth()
)
```

**Exemple complet :**
```kotlin
@Composable
fun PhotoCard(photo: MarsPhoto) {
    Card {
        Column {
            AsyncImage(
                model = photo.imageUrl,
                contentDescription = "Photo Mars ${photo.id}",
                error = painterResource(R.drawable.ic_broken_image),
                placeholder = painterResource(R.drawable.loading_img)
            )
            Text("ID: ${photo.id}")
        }
    }
}
```

### 7.4 Gestion d'État UI

**États possibles (sealed class) :**
```kotlin
sealed class UiState {
    object Loading : UiState()
    data class Success(val data: List<Item>) : UiState()
    data class Error(val message: String) : UiState()
}
```

**Affichage conditionnel :**
```kotlin
@Composable
fun MarsPhotosScreen() {
    val viewModel: MarsViewModel = viewModel()
    val uiState by viewModel.uiState.collectAsState()
    
    when (val state = uiState) {
        is UiState.Loading -> CircularProgressIndicator()
        is UiState.Success -> PhotoGrid(state.data)
        is UiState.Error -> ErrorMessage(state.message)
    }
}
```

**Exemple complet :**
```kotlin
sealed class UiState {
    object Loading : UiState()
    data class Success(val photos: List<MarsPhoto>) : UiState()
    data class Error(val message: String) : UiState()
}

@Composable
fun HomeScreen() {
    val viewModel: MarsViewModel = viewModel()
    val uiState by viewModel.uiState.collectAsState()
    
    when (uiState) {
        is UiState.Loading -> {
            Box(modifier = Modifier.fillMaxSize()) {
                CircularProgressIndicator(Modifier.align(Alignment.Center))
            }
        }
        is UiState.Success -> {
            LazyVerticalGrid(
                columns = GridCells.Fixed(2)
            ) {
                items(uiState.photos) { photo ->
                    PhotoCard(photo)
                }
            }
        }
        is UiState.Error -> {
            Column(
                modifier = Modifier.fillMaxSize(),
                horizontalAlignment = Alignment.CenterHorizontally
            ) {
                Text("Erreur: ${uiState.message}")
                Button(onClick = { viewModel.loadPhotos() }) {
                    Text("Réessayer")
                }
            }
        }
    }
}
```

### 7.5 Gestion des Erreurs

**Exceptions courantes :**
- `IOException` : erreur réseau (ex: pas de connexion)
- `HttpException` : erreur HTTP (ex: 404 Not Found, 500 Server Error)
- `SerializationException` : erreur de parsing JSON

**Try-catch :**
```kotlin
try {
    val result = apiService.getData()
    _uiState.value = UiState.Success(result)
} catch (e: IOException) {
    _uiState.value = UiState.Error("Erreur réseau: ${e.message}")
} catch (e: HttpException) {
    _uiState.value = UiState.Error("Erreur HTTP: ${e.code()}")
} catch (e: Exception) {
    _uiState.value = UiState.Error("Erreur: ${e.message}")
}
```

**Exemple complet :**
```kotlin
fun loadData() {
    viewModelScope.launch {
        _uiState.value = UiState.Loading
        try {
            val data = apiService.getPhotos()
            _uiState.value = UiState.Success(data)
        } catch (e: IOException) {
            _uiState.value = UiState.Error("Vérifiez votre connexion")
        } catch (e: HttpException) {
            when (e.code()) {
                404 -> _uiState.value = UiState.Error("Ressource non trouvée")
                500 -> _uiState.value = UiState.Error("Erreur serveur")
                else -> _uiState.value = UiState.Error("Erreur HTTP: ${e.code()}")
            }
        } catch (e: Exception) {
            _uiState.value = UiState.Error("Erreur inattendue")
        }
    }
}
```

---

## 8. POINTS CLÉS POUR QCM

### Kotlin
- **Nullabilité** : `String?` = nullable, `?.` = safe call, `?:` = Elvis (ex: `val x = y ?: 0`)
- **Data classes** : génèrent automatiquement `equals()`, `hashCode()`, `toString()`, `copy()`
- **val vs var** : `val` = immuable, `var` = mutable
- **Fonctions d'extension** : `fun String.capitalize()`
- **Lambdas** : `list.map { it * 2 }` où `it` = élément courant

### Android / Compose
- **@Composable** : fonction qui peut être recomposée
- **remember** : mémorise une valeur pendant la recomposition
- **mutableStateOf** : crée un état observable (ex: `var x by remember { mutableStateOf(0) }`)
- **rememberSaveable** : persiste l'état lors des rotations (ex: `var x by rememberSaveable { mutableStateOf(0) }`)
- **LazyColumn** : liste verticale avec chargement paresseux (ex: `LazyColumn { items(list) { Item(it) } }`)
- **StateFlow** : état observable réactif (ex: `val state: StateFlow<Type> = _state.asStateFlow()`)

### Architecture
- **ViewModel** : survit aux changements de configuration (rotation)
- **StateFlow** : état observable thread-safe
- **collectAsState()** : collecte un Flow dans Compose (ex: `val state by viewModel.state.collectAsState()`)
- **Cycle de vie** : `onCreate` → `onStart` → `onResume` → `onPause` → `onStop` → `onDestroy`

### Coroutines
- **suspend** : fonction qui peut être suspendue (ex: `suspend fun fetch() { delay(1000) }`)
- **launch** : lance une coroutine (ex: `viewModelScope.launch { }`)
- **delay()** : pause non-bloquante (ex: `delay(1000)` = 1 seconde)
- **LaunchedEffect** : exécute du code suspendu dans Compose (ex: `LaunchedEffect(Unit) { }`)
- **viewModelScope** : scope de coroutine lié au ViewModel

### Réseau
- **Retrofit** : bibliothèque pour appels HTTP
- **@GET, @POST** : annotations pour méthodes HTTP (ex: `@GET("photos") suspend fun getPhotos()`)
- **suspend** : fonctions de service doivent être suspendues
- **kotlinx.serialization** : sérialisation JSON (ex: `@Serializable data class User(...)`)
- **Coil / AsyncImage** : chargement d'images (ex: `AsyncImage(model = url, contentDescription = null)`)
- **Gestion d'erreur** : `try-catch` avec `IOException` et `HttpException`

---

## 9. FORMULAIRE RAPIDE

### Syntaxe Essentielle

**Variable :**
```kotlin
val immuable = 5        // Ne peut pas changer
var mutable = 10       // Peut changer
```

**Fonction :**
```kotlin
fun nom(param: Type): Retour = expression
// Ex: fun add(a: Int, b: Int): Int = a + b
```

**Classe :**
```kotlin
class Nom(val prop: Type) {
    fun methode() { }
}
// Ex: class User(val name: String) { fun greet() = "Hello $name" }
```

**Data class :**
```kotlin
data class Nom(val prop1: Type1, val prop2: Type2)
// Ex: data class Person(val name: String, val age: Int)
```

**Composable :**
```kotlin
@Composable
fun Nom() {
    Text("Hello")
}
```

**État :**
```kotlin
var state by remember { mutableStateOf(valeur) }
// Ex: var count by remember { mutableStateOf(0) }
```

**ViewModel :**
```kotlin
class MyViewModel : ViewModel() {
    private val _state = MutableStateFlow(initial)
    val state: StateFlow<Type> = _state.asStateFlow()
}
```

**Coroutine :**
```kotlin
viewModelScope.launch {
    suspend fun maFonction() { }
}
```

**API :**
```kotlin
@GET("endpoint")
suspend fun getData(): Type
```

---

**Bon courage pour votre QCM ! 🚀**
