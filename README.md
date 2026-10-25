if (moveLeft) {
    playerX -= speed;
}
if (moveRight) {
    playerX += speed;
}
enemyY += enemySpeed;
if (enemyY > screenHeight) {
    enemyY = -enemyHeight;
    score++;
}
score++;
score += 10;
Rect playerRect = new Rect(playerX, playerY,
        playerX + playerWidth,
        playerY + playerHeight);

Rect enemyRect = new Rect(enemyX, enemyY,
        enemyX + enemyWidth,
        enemyY + enemyHeight);

if (Rect.intersects(playerRect, enemyRect)) {
    gameOver = true;
}
if (gameOver) {
    canvas.drawText("GAME OVER", 300, 500, paint);
}
ArrayList<EnemyCar> enemies = new ArrayList<>();

for(int i = 0; i < 5; i++) {
    enemies.add(new EnemyCar());
}
for(EnemyCar enemy : enemies) {
    enemy.update();
}
if(score > 100) {
    enemySpeed = 15;
}

if(score > 300) {
    enemySpeed = 20;
}

if(score > 500) {
    enemySpeed = 25;
}
enemySpeed = 10 + (score / 100);
SharedPreferences prefs =
getSharedPreferences("GameData", MODE_PRIVATE);

int highScore =
prefs.getInt("highscore", 0);
if(score > highScore){
    prefs.edit()
         .putInt("highscore", score)
         .apply();
}
MediaPlayer crash =
MediaPlayer.create(this,R.raw.crash);
crash.start();
boolean paused = false;
paused = true;
paused = false;
if(!paused){
    updateGame();
}
class Coin {
    int x;
    int y;
}
if(playerRect.intersects(coinRect)){
    coins++;
}
PLAY
GARAGE
MISSIONS
DAILY REWARD
LEADERBOARD
SETTINGS
EXIT
Car 1 (Free)
Car 2 (500 Coins)
Car 3 (1000 Coins)
Car 4 (2000 Coins)
Engine +1
Handling +1
Turbo +1
Armor +1
carSpeed += 2;
Day 1 = 100 Coins
Day 2 = 200 Coins
Day 3 = Shield
Day 4 = 300 Coins
Day 5 = Turbo
Day 6 = 500 Coins
Day 7 = Premium Car
Drive 1000m
Collect 100 Coins
Reach Score 500
Unlock 3 Cars
Play 7 Days
Coins
Cars
Power-Ups
1v1 Match
4 Player Race
Friends Challenge
Global Matchmaking
Firebase Realtime Database
Photon Unity Networking
Highest Score
Longest Distance
Most Coins
1000 Coins = Desert
3000 Coins = Snow
Watch Ad
↓
Get 200 Coins
Extra Life
Shield
Turbo
Playable game
Basic graphics
Basic controls
3-5 enemy cars
Random lanes
Road lines
Scrolling background
Engine
Coin
Crash
Button clicks
More challenging gameplay
Improved visuals
Collect while driving
SharedPreferences
Store total coins
Distance reward
Coin reward
Persistent player progress
Car 1 Free
Car 2 500 Coins
Car 3 1000 Coins
Car 4 2000 Coins
Upgrade Engine
Upgrade Handling
Upgrade Armor
Store purchased cars
Progression system
One free crash
Temporary boost
Attract coins
Slow enemy traffic
Strategic gameplay
Default map
Unlock with coins
Premium area
Multiple environments
Drive 1000m
Collect 500 Coins
Reach Score 1000
Play 10 Games
Master Driver
Coin Collector
Road King
Speed Demon
Long-term goals
Day 1 = 100 Coins
Day 2 = 200 Coins
Day 3 = Shield
Day 4 = 300 Coins
Day 5 = Turbo
Day 6 = 500 Coins
Day 7 = New Car
Improve player retention
Main Menu
Watch ad
↓
Get Coins
Revenue generation
Highest Score
Longest Distance
Global competition
1 vs 1
4 Player Race
Tournament
Social gameplay
Build
↓
Generate Signed Bundle
↓
AAB
Game Icon
Feature Graphic
Screenshots
Privacy Policy
Google Play StoreCar Racing Game
│
├─ Main Menu
├─ Play
├─ Garage
├─ Cars
├─ Upgrades
├─ Coins
├─ Power-Ups
├─ Themes
├─ Missions
├─ Achievements
├─ Daily Rewards
├─ Leaderboards
├─ Multiplayer
├─ AdMob
└─ Play Store ReleaseCarRacingGame/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/vinay/carracing/
│   │   │   │
│   │   │   ├── activities/
│   │   │   │   ├── SplashActivity.java
│   │   │   │   ├── MainMenuActivity.java
│   │   │   │   ├── GameActivity.java
│   │   │   │   ├── GarageActivity.java
│   │   │   │   ├── CarSelectionActivity.java
│   │   │   │   ├── MissionActivity.java
│   │   │   │   ├── RewardActivity.java
│   │   │   │   └── SettingsActivity.java
│   │   │   │
│   │   │   ├── game/
│   │   │   │   ├── GameView.java
│   │   │   │   ├── GameLoop.java
│   │   │   │   ├── CollisionManager.java
│   │   │   │   ├── SpawnManager.java
│   │   │   │   └── ScoreManager.java
│   │   │   │
│   │   │   ├── player/
│   │   │   │   ├── PlayerCar.java
│   │   │   │   ├── PlayerData.java
│   │   │   │   └── PlayerStats.java
│   │   │   │
│   │   │   ├── enemies/
│   │   │   │   ├── EnemyCar.java
│   │   │   │   ├── Truck.java
│   │   │   │   └── PoliceCar.java
│   │   │   │
│   │   │   ├── powerups/
│   │   │   │   ├── Shield.java
│   │   │   │   ├── Turbo.java
│   │   │   │   ├── Magnet.java
│   │   │   │   └── SlowMotion.java
│   │   │   │
│   │   │   ├── rewards/
│   │   │   │   ├── DailyRewardManager.java
│   │   │   │   └── RewardItem.java
│   │   │   │
│   │   │   ├── missions/
│   │   │   │   ├── Mission.java
│   │   │   │   ├── MissionManager.java
│   │   │   │   └── AchievementManager.java
│   │   │   │
│   │   │   ├── garage/
│   │   │   │   ├── CarData.java
│   │   │   │   ├── UpgradeManager.java
│   │   │   │   └── InventoryManager.java
│   │   │   │
│   │   │   ├── ads/
│   │   │   │   ├── BannerAds.java
│   │   │   │   ├── RewardAds.java
│   │   │   │   └── InterstitialAds.java
│   │   │   │
│   │   │   ├── online/
│   │   │   │   ├── FirebaseManager.java
│   │   │   │   ├── LeaderboardManager.java
│   │   │   │   └── MultiplayerManager.java
│   │   │   │
│   │   │   ├── audio/
│   │   │   │   ├── SoundManager.java
│   │   │   │   └── MusicManager.java
│   │   │   │
│   │   │   ├── storage/
│   │   │   │   ├── SaveManager.java
│   │   │   │   ├── PreferenceHelper.java
│   │   │   │   └── HighScoreManager.java
│   │   │   │
│   │   │   └── utils/
│   │   │       ├── Constants.java
│   │   │       ├── Helpers.java
│   │   │       └── GameConfig.java
│   │   │
│   │   ├── res/
│   │   │
│   │   ├── drawable/
│   │   │   ├── cars/
│   │   │   ├── enemies/
│   │   │   ├── roads/
│   │   │   ├── buttons/
│   │   │   └── ui/
│   │   │
│   │   ├── raw/
│   │   │   ├── engine.mp3
│   │   │   ├── crash.wav
│   │   │   ├── coin.wav
│   │   │   ├── turbo.wav
│   │   │   └── background_music.mp3
│   │   │
│   │   ├── anim/
│   │   │   ├── fade_in.xml
│   │   │   ├── fade_out.xml
│   │   │   └── zoom.xml
│   │   │
│   │   ├── layout/
│   │   │   ├── activity_main.xml
│   │   │   ├── activity_game.xml
│   │   │   ├── activity_garage.xml
│   │   │   ├── activity_rewards.xml
│   │   │   ├── activity_missions.xml
│   │   │   └── activity_settings.xml
│   │   │
│   │   └── values/
│   │       ├── strings.xml
│   │       ├── colors.xml
│   │       ├── themes.xml
│   │       └── dimens.xml
│   │
│   └── AndroidManifest.xml
│
├── assets/
│   ├── city_theme/
│   ├── desert_theme/
│   ├── snow_theme/
│   └── icons/
│
├── screenshots/
│
├── docs/
│   ├── roadmap.md
│   ├── database_design.md
│   └── game_design_document.md
│
└── release/
    ├── apk/
    └── aab/Phase 1
├─ PlayerCar
├─ EnemyCar
├─ CollisionManager
└─ ScoreManager

Phase 2
├─ Coins
├─ Sounds
├─ High Scores
└─ Pause System

Phase 3
├─ Garage
├─ Car Selection
└─ Upgrades

Phase 4
├─ Missions
├─ Rewards
└─ Achievements

Phase 5
├─ Themes
├─ AdMob
└─ Leaderboards

Phase 6
└─ Multiplayerpackage com.vinay.carracing;

import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private GameView gameView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        gameView = new GameView(this);
        setContentView(gameView);
    }
}
package com.vinay.carracing;

import android.graphics.Rect;

public class PlayerCar {

    int x;
    int y;

    int width = 150;
    int height = 250;

    public PlayerCar(int x, int y) {
        this.x = x;
        this.y = y;
    }

    public Rect getRect() {
        return new Rect(
                x,
                y,
                x + width,
                y + height
        );
    }
}
package com.vinay.carracing;

import android.graphics.Rect;

public class EnemyCar {

    int x;
    int y;

    int width = 150;
    int height = 250;

    int speed = 15;

    public EnemyCar(int x, int y) {
        this.x = x;
        this.y = y;
    }

    public void update() {
        y += speed;
    }

    public Rect getRect() {
        return new Rect(
                x,
                y,
                x + width,
                y + height
        );
    }
}
package com.vinay.carracing;

import android.graphics.Rect;

public class CollisionManager {

    public static boolean check(
            PlayerCar player,
            EnemyCar enemy
    ) {
        return Rect.intersects(
                player.getRect(),
                enemy.getRect()
        );
    }
}
package com.vinay.carracing;

public class ScoreManager {

    private int score = 0;

    public void increase() {
        score++;
    }

    public int getScore() {
        return score;
    }
}
package com.vinay.carracing;

import android.content.Context;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;
import android.view.MotionEvent;
import android.view.SurfaceHolder;
import android.view.SurfaceView;

public class GameView extends SurfaceView
        implements Runnable {

    private Thread thread;
    private boolean running = true;

    private PlayerCar player;
    private EnemyCar enemy;

    private Paint paint;

    private ScoreManager scoreManager;

    private boolean gameOver = false;

    public GameView(Context context) {
        super(context);

        paint = new Paint();

        player = new PlayerCar(
                400,
                1400
        );

        enemy = new EnemyCar(
                400,
                -300
        );

        scoreManager = new ScoreManager();

        thread = new Thread(this);
        thread.start();
    }

    @Override
    public void run() {

        while (running) {

            if (!gameOver) {

                enemy.update();

                if (enemy.y > getHeight()) {

                    enemy.y = -300;

                    scoreManager.increase();
                }

                if (CollisionManager.check(
                        player,
                        enemy
                )) {
                    gameOver = true;
                }
            }

            drawGame();

            try {
                Thread.sleep(16);
            } catch (Exception e) {
                e.printStackTrace();
            }
        }
    }

    private void drawGame() {

        if (!getHolder().getSurface().isValid())
            return;

        Canvas canvas =
                getHolder().lockCanvas();

        canvas.drawColor(Color.DKGRAY);

        paint.setColor(Color.BLUE);

        canvas.drawRect(
                player.x,
                player.y,
                player.x + player.width,
                player.y + player.height,
                paint
        );

        paint.setColor(Color.RED);

        canvas.drawRect(
                enemy.x,
                enemy.y,
                enemy.x + enemy.width,
                enemy.y + enemy.height,
                paint
        );

        paint.setColor(Color.WHITE);
        paint.setTextSize(70);

        canvas.drawText(
                "Score: " +
                        scoreManager.getScore(),
                50,
                100,
                paint
        );

        if (gameOver) {

            paint.setTextSize(120);

            canvas.drawText(
                    "GAME OVER",
                    180,
                    800,
                    paint
            );
        }

        getHolder().unlockCanvasAndPost(canvas);
    }

    @Override
    public boolean onTouchEvent(MotionEvent event) {

        if (event.getAction()
                == MotionEvent.ACTION_DOWN) {

            if (event.getX()
                    < getWidth() / 2) {

                player.x -= 150;

            } else {

                player.x += 150;
            }
        }

        return true;
    }
}
<application
    android:label="Car Racing"
    android:theme="@style/Theme.AppCompat.Light">

    <activity
        android:name=".MainActivity">

        <intent-filter>
            <action android:name=
                "android.intent.action.MAIN"/>

            <category android:name=
                "android.intent.category.LAUNCHER"/>
        </intent-filter>

    </activity>

</application>
