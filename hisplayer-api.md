# HISPlayer API

## Public API
The following public APIs are provided by **HISPlayerManager**.

## Functions
Use the following UFunctions in your blueprint or script to make your custom HISPlayer implementation.

#### static void BeginPlay(int numStreams) // HISPlayer BeginPlay
Pre-initialize HISPlayer. You must call this function on BeginPlay before the SetUp.
  * **Param1**: The number of streams to instantiate.

#### static void Setup(int streamIndex, UTexture2D*& outputTexture) // HISPlayer Setup
Initialize HISPlayer. It creates a texture in runtime internally.
  * **Param1**: Stream index.
  * **Param2**: Result texture reference.

#### static int OpenPlayer(int streamIndex, const FString& url) // HISPlayer Open Player
Start HISPlayer. A valid URL must be passed as parameter.
  * **Param1**: Stream index.
  * **Param2**: Content URL.
  * **Return**: 0 on success.

#### static void SetPlayBackProperties (int streamIndex, const FHISPlayerPlaybackProperties& Properties) // HISPlayer Set PlayBack Properties
Set the playback properties.
  * **Param1**: Stream index.
  * **Param2**: HISPlayer playback properties to set.

#### static FHISPlayerPlaybackProperties& GetPlaybackProperties(int streamIndex) // HISPlayer Set PlayBack Properties
Get the current playback properties.
  * **Param1**: Stream index.
  * **Return**: The actual stream's HISPlayer playback properties.

#### static void Update(int streamIndex) // HISPlayer Update
Update each frame, needs to be called every frame.
  * **Param1**: Stream index.

#### static void Resume(int streamIndex) // HISPlayer Resume
Update each frame, needs to be called every frame.
  * **Param1**: Stream index.

#### static void Pause(int streamIndex) // HISPlayer Pause
Pause the video.
  * **Param1**: Stream index.

#### static void Stop(int streamIndex) // HISPlayer Stop
Stop the video and, next time it's played, it will begin from start.
  * **Param1**: Stream index.

#### static void Seek(int streamIndex, int msec) // HISPlayer Seek
Seeks the video to a certain position
  * **Param1**: Stream index.
  * **Param2**: Position to seek in miliseconds.

#### static void SetVolume(int streamIndex, float newVolume) // HISPlayer Set Volume
Set Playback volume.
  * **Param1**: Stream index.
  * **Param2**: Must be included in the range [0.0f, 1.0f].

#### static void SetMute(int streamIndex, bool Mute) // HISPlayer Set Mute
Mute the current audio.
  * **Param1**: Stream index.
  * **Param2**: True for mute, False for unmute.

#### static bool SetLooping(int streamIndex, bool looping) // HISPlayer Set Looping
Enable or disable looping.
  * **Param1**: Stream index.
  * **Param2**: Whether the looping should be enabled or disabled.
  * **Return**: True on success, False otherwise.

#### static void ChangeVideoContent(int streamIndex, const FString & url) // HISPlayer Change Video Content
Change the content of one player instance on runtime.
  * **Param1**: Stream index.
  * **Param2**: Content URL.

#### static int GetPlaybackPosition(int streamIndex) // HISPlayer Get Playback Position
Returns the current time position of the current content.
  * **Param1**: Stream index.
  * **Return**: Returns the current time position of the current track in miliseconds.

#### static int GetTotalPlaybackTime(int streamIndex) // HISPlayer Get Total Playback Time
Returns the total time of the current content.
  * **Param1**: Stream index.
  * **Return**: Returns the current time position of the current track in miliseconds.

#### static void Close(int streamIndex) // HISPlayer Close
Must be called for closing and releasing HISPlayer.
  * **Param1**: Stream index.

#### static UDelegateManager* Getdelegatemanager(int streamIndex) // HISPlayer Get Delegate Manager
Get the Delegate Manager.
  * **Param1**: Stream index.
  * **Return**: Delegate manager reference.

#### static HISPlayerStatus GetPlayerStatus(int streamIndex) // HISPlayer Get Player Status
Get the current player status.
  * **Param1**: Stream index.
  * **Return**: Stream status as a HISPlayerStatus type.

#### static void CreateNewTexture(int streamIndex, FIntPoint resolution, UTexture2D*& outputTexture) // HISPlayer Create New Texture 
 Create a new texture of a new resolution for a particular stream.
  * **Param1**: Stream index.
  * **Param2**: FIntPoint for resolution. X value for Width, Y value for Height.
  * **Param3**: Result texture reference.

#### static void EnableRendering(int streamIndex, bool enable) // HISPlayer Enable Rendering
  Use this function to enable or disable the rendering of one stream. The audio will keep playing. 
  Can be used in single or multistream to disable the stream rendering when the stream visuals are not in the visual field of the player, 
  in order to improve performance.
  * **Param1**: Stream index.
  * **Param2**: True for rendering enabled, false for disable it.

#### static void SetLogLevel(HISPlayerLogLevel logLevel) // HISPlayer Set Log Level
 Use this method to set the log level of the HISPlayer plugin. There are 5 levels: Debug, Info, Warning, Error and None.
 * **Param1**: HISPlayer Log Level:
 	- If Debug is settled, you will get Debug, Info, Warning and Error logs.
 	- If Info is selected, you will get Info, Warning and Error logs.
 	- If Warning is selected, you will get Warning and Error logs.
 	- If Error is selected, you will only get Error logs.
 	- If None is selected, no log will be displayerd.
