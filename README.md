# MacaroniTheIII
I am a random kid from a random school who wants to play games.


Go to youranidiot.com for free V-bucks


"I just rizzed up the ohio goon max lord with a sigma who is skibidi grimace shake"- Some weird kid somewhere


People, you do not have knee surgery tommorow


Snake Game
<iframe src="https://snakegame.org/" width="100%" height="600" frameborder="0" scrolling="no"></iframe>


Eaglercraft
<iframe src="https://eaglercraft.com/mc/1.8.8/" width="100%" height="700" frameborder="0" scrolling="no"></iframe>


Slope (Every single game website ever has this)
<iframe src="https://slopegameio.github.io/" width="75%" height="500" frameborder="10" scrolling="no"></iframe>


Five Nights at Winstons
<iframe src="https://g.deev.is/fnaw/" width="100%" height="800" frameborder="0" scrolling="no"></iframe>



bool _isFullscreen = false;
bool _isBorderless = false;
int _width = 0;
int _height = 0;
GraphicsDeviceManager _graphics;
GameWindow _window;

public void ToggleFullscreen() {
    bool oldIsFullscreen = _isFullscreen;

    if (_isBorderless) {
        _isBorderless = false;
    } else {
        _isFullscreen = !_isFullscreen;
    }

    ApplyFullscreenChange(oldIsFullscreen);
}
public void ToggleBorderless() {
    bool oldIsFullscreen = _isFullscreen;

    _isBorderless = !_isBorderless;
    _isFullscreen = _isBorderless;

    ApplyFullscreenChange(oldIsFullscreen);
}

private void ApplyFullscreenChange(bool oldIsFullscreen) {
    if (_isFullscreen) {
        if (oldIsFullscreen) {
            ApplyHardwareMode();
        } else {
            SetFullscreen();
        }
    } else {
        UnsetFullscreen();
    }
}
private void ApplyHardwareMode() {
    _graphics.HardwareModeSwitch = !_isBorderless;
    _graphics.ApplyChanges();
}
private void SetFullscreen() {
    _width = Window.ClientBounds.Width;
    _height = Window.ClientBounds.Height;

    _graphics.PreferredBackBufferWidth = GraphicsAdapter.DefaultAdapter.CurrentDisplayMode.Width;
    _graphics.PreferredBackBufferHeight = GraphicsAdapter.DefaultAdapter.CurrentDisplayMode.Height;
    _graphics.HardwareModeSwitch = !_isBorderless;

    _graphics.IsFullScreen = true;
    _graphics.ApplyChanges();
}
private void UnsetFullscreen() {
    _graphics.PreferredBackBufferWidth = _width;
    _graphics.PreferredBackBufferHeight = _height;
    _graphics.IsFullScreen = false;
    _graphics.ApplyChanges();
}
To use this, call either ToggleFullscreen or ToggleBorderless.

Explanation
Track the current fullscreen state. Initialized to false since the game starts in window mode.

bool _isFullscreen = false;
bool _isBorderless = false;

THE END
