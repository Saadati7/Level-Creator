
// Use this for Store All Levels
[System.Serializable]
public class Levels
{
    [HideInInspector]
    public int LevelTimer = 0; // Set Timer for Those Level End with Clock Down Timer
    public EachWave[] Waves = null;
}

// Use this for Store all Waves on Specific Level
 [System.Serializable]
public class EachWave
{
    [HideInInspector]
    public float waveStartTime = 1.0f; // Set Time to make delay from start wave
    public EnemyProperties[] Enemys = null;
}

// Use this for Store Enemy’s properties 
[System.Serializable]
public class EnemyProperties
{
    [HideInInspector]
    public GameObject Enemy = null;
    public float startTime = 1.0f;
    public int numberOfEnemy = 1;
    public float interval = 1.0f;
}


public class scLevels : MonoBehaviour
{
    public static scLevels instance;

    public Levels[] levels;
    public GameObject wavePrefab; // Wave script launcher, Set Current Wave Data and properties
    public GameObject spawner; // Enemy Spawner position
    public GameObject troopsSpawner; // Player’s warrior Spawner position
    public GameObject heroSpawner; // Player’s avatar Spawner position
    public bool isGameStarted = false;
    public List<GameObject> AllWaves;


    private GameObject MyWave;
    private bool isFinishedWaveMaker = false;


    void Start()
    {
        instance = this;
    }

    void Update()
    {
        if (isGameStarted)
        {
            if (isFinishedWaveMaker == false)
            {
                for (int i = 0; i < levels[scGameManager.instance.PlayerInLevel].Waves.Length; i++) // create wave/s by last level player reached
                {
                    for (int j = 0; j < levels[scGameManager.instance.PlayerInLevel].Waves[i].Enemys.Length; j++)
                    {
                        StartCoroutine(CreatingWave(levels[scGameManager.instance.PlayerInLevel].Waves[i].waveStartTime, i, j));
                    }
                }
                isFinishedWaveMaker = true;
                isGameStarted = false;
            }
        }

    }
