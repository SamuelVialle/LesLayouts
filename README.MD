*** Les Layouts

1 - Changer le ConstraintLayout par un FrameLayout dans le code XML
    Voir la différence de position
    Faire le tour des attributs bg, margin, padding ....
2 - En profiter pour faire le tour des views en plus
3 - La cardView 
    Modification depuis le xml 
    Ajout de composants dans le Cardview en expliquant les chevrons du XML
4 - Le Linear Vertical
    Ajout de composants dans le Linear en expliquant l'attribut weightsum // weight // le margin
4 - Le Linear Horizontal
    Ajout de composant dans le Linear
5 - On recommence pour tout bien positionner
6 - Ajout des divider et des views
7 - Le spacer pour créer des espaces vides
8 - Le scrollView

9 - Le binding
 Dans la section android du fichier gradle.module ajouter :
    buildFeatures {
        viewBinding = true
    }
 Dans l'activité qui sera liée au design ajouter le code suivant :
    Ajouter la variable globale :
        lateinit var binding: ActivityMainBinding
    Puis remplacer ces lignes dans la méthode onCreate
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContentView(R.layout.activity_main)
    Par
        méthode 1
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            binding = ActivityMainBinding.inflate(layoutInflater)
            setContentView(binding.root)
        méthode 2
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            val inflater = LayoutInflater.from(this)
            binding = ActivityMainBinding.inflate(inflater)
            setContentView(binding.root)
        La méthode 1 est à préferer car le layoutInflater est initialisé directement avec la méthode onCreate
        
    Il ne reste plus qu'à appeler les id des différentes vues de al façon suivante :
        binding.lIdDeLaVueSurLaquelleOnVeutTravaillerDansLeCode.action = qqchose
        ie. binding.textView.text = "ici le texte"

10 - Les styles exemple avec Dark and light text color



