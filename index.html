import { useState, useEffect } from 'react';
import { Button } from '@/components/ui/button';
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';
import { useTextSetting } from '@/lib/editable-settings';
import { Switch } from '@/components/ui/switch';
import { Label } from '@/components/ui/label';
import { Input } from '@/components/ui/input';
import { Dialog, DialogContent, DialogHeader, DialogTitle, DialogTrigger } from '@/components/ui/dialog';
import { Textarea } from '@/components/ui/textarea';

export default function Block() {
  const [mode, setMode] = useState('games');
  const [keyBuffer, setKeyBuffer] = useState('');
  const [selectedGame, setSelectedGame] = useState(null);
  const [calcDisplay, setCalcDisplay] = useState('0');
  const [calcBuffer, setCalcBuffer] = useState('');
  
  // Admin settings
  const [websiteEnabled, setWebsiteEnabled] = useState(true);
  const [offlineMessage, setOfflineMessage] = useState('The game hub is currently under maintenance. Please check back later!');
  const [themes, setThemes] = useState([
    { id: 1, name: 'Default', bgColor: '#ffffff', tileColor: '#f8f9fa', textColor: '#21262e', buttonColor: '#21262e' },
    { id: 2, name: 'Dark Mode', bgColor: '#1a1a1a', tileColor: '#2d2d2d', textColor: '#ffffff', buttonColor: '#4a9eff' },
    { id: 3, name: 'Ocean', bgColor: '#e0f2fe', tileColor: '#bae6fd', textColor: '#0c4a6e', buttonColor: '#0284c7' }
  ]);
  const [currentTheme, setCurrentTheme] = useState(themes[0]);
  const [showThemeCreator, setShowThemeCreator] = useState(false);
  const [newTheme, setNewTheme] = useState({
    name: '',
    bgColor: '#ffffff',
    tileColor: '#f8f9fa',
    textColor: '#21262e',
    buttonColor: '#21262e'
  });

  const pageTitle = useTextSetting({
    name: 'page-title',
    label: 'Page Title',
    initialValue: 'Calculator Online',
  });

  // Keyboard listener for SOS and 6006 triggers
  useEffect(() => {
    const handleKeyPress = (e) => {
      if (e.target.tagName === 'INPUT' || e.target.tagName === 'TEXTAREA') return;
      
      const newBuffer = (keyBuffer + e.key.toLowerCase()).slice(-4);
      setKeyBuffer(newBuffer);
      
      if (newBuffer.slice(-3) === 'sos') {
        setMode('calculator');
        setKeyBuffer('');
      }
      
      if (newBuffer === '6006') {
        setMode('admin');
        setKeyBuffer('');
      }
      
      if (newBuffer === 'exit') {
        setMode('games');
        setKeyBuffer('');
      }
    };

    window.addEventListener('keypress', handleKeyPress);
    return () => window.removeEventListener('keypress', handleKeyPress);
  }, [keyBuffer]);

  // Calculator logic
  const handleCalcInput = (value) => {
    const newBuffer = calcBuffer + value;
    setCalcBuffer(newBuffer);
    setCalcDisplay(newBuffer || '0');
    
    if (newBuffer === '67') {
      setMode('games');
      setCalcDisplay('0');
      setCalcBuffer('');
    }
  };

  const clearCalc = () => {
    setCalcDisplay('0');
    setCalcBuffer('');
  };

  const calculateResult = () => {
    try {
      const result = eval(calcBuffer);
      setCalcDisplay(String(result));
      setCalcBuffer(String(result));
    } catch {
      setCalcDisplay('Error');
      setCalcBuffer('');
    }
  };

  const createTheme = () => {
    if (!newTheme.name.trim()) return;
    const theme = { ...newTheme, id: Date.now() };
    setThemes([...themes, theme]);
    setNewTheme({
      name: '',
      bgColor: '#ffffff',
      tileColor: '#f8f9fa',
      textColor: '#21262e',
      buttonColor: '#21262e'
    });
    setShowThemeCreator(false);
  };

  const deleteTheme = (id) => {
    setThemes(themes.filter(t => t.id !== id));
    if (currentTheme.id === id) {
      setCurrentTheme(themes[0]);
    }
  };

  const panicButton = (
    <Button 
      onClick={() => {
        setMode('calculator');
        setSelectedGame(null);
      }}
      variant="destructive" 
      className="fixed top-4 right-4 z-50 shadow-lg"
      size="sm"
    >
      Emergency
    </Button>
  );

  // Admin Panel
  if (mode === 'admin') {
    return (
      <div className="min-h-screen" style={{ backgroundColor: currentTheme.bgColor, color: currentTheme.textColor }}>
        <div className="container py-8">
          <div className="content max-w-4xl mx-auto">
            <div className="flex justify-between items-center mb-8">
              <h1 className="font-heading text-4xl">Admin Panel - Taylor</h1>
              <Button onClick={() => setMode('games')} variant="outline">Exit Admin</Button>
            </div>

            {/* Website Control */}
            <Card className="mb-6" style={{ backgroundColor: currentTheme.tileColor, color: currentTheme.textColor, borderColor: currentTheme.textColor + '20' }}>
              <CardHeader>
                <CardTitle>Website Control</CardTitle>
              </CardHeader>
              <CardContent className="space-y-4">
                <div className="flex items-center justify-between">
                  <Label htmlFor="website-toggle" className="text-lg">Website Status</Label>
                  <div className="flex items-center gap-3">
                    <span className={websiteEnabled ? 'text-green-600 font-semibold' : 'text-red-600 font-semibold'}>
                      {websiteEnabled ? 'Online' : 'Offline'}
                    </span>
                    <Switch 
                      id="website-toggle"
                      checked={websiteEnabled}
                      onCheckedChange={setWebsiteEnabled}
                    />
                  </div>
                </div>
                <div>
                  <Label htmlFor="offline-message">Offline Message</Label>
                  <Textarea
                    id="offline-message"
                    value={offlineMessage}
                    onChange={(e) => setOfflineMessage(e.target.value)}
                    className="mt-2"
                    rows={3}
                  />
                </div>
              </CardContent>
            </Card>

            {/* Theme Management */}
            <Card style={{ backgroundColor: currentTheme.tileColor, color: currentTheme.textColor, borderColor: currentTheme.textColor + '20' }}>
              <CardHeader>
                <div className="flex justify-between items-center">
                  <CardTitle>Theme Management</CardTitle>
                  <Dialog open={showThemeCreator} onOpenChange={setShowThemeCreator}>
                    <DialogTrigger asChild>
                      <Button style={{ backgroundColor: currentTheme.buttonColor, color: '#ffffff' }}>
                        Create Theme
                      </Button>
                    </DialogTrigger>
                    <DialogContent>
                      <DialogHeader>
                        <DialogTitle>Create New Theme</DialogTitle>
                      </DialogHeader>
                      <div className="space-y-4 py-4">
                        <div>
                          <Label htmlFor="theme-name">Theme Name</Label>
                          <Input
                            id="theme-name"
                            value={newTheme.name}
                            onChange={(e) => setNewTheme({...newTheme, name: e.target.value})}
                            placeholder="My Custom Theme"
                            className="mt-2"
                          />
                        </div>
                        <div>
                          <Label htmlFor="bg-color">Background Color</Label>
                          <div className="flex gap-2 mt-2">
                            <Input
                              id="bg-color"
                              type="color"
                              value={newTheme.bgColor}
                              onChange={(e) => setNewTheme({...newTheme, bgColor: e.target.value})}
                              className="w-20 h-10"
                            />
                            <Input
                              value={newTheme.bgColor}
                              onChange={(e) => setNewTheme({...newTheme, bgColor: e.target.value})}
                              className="flex-1"
                            />
                          </div>
                        </div>
                        <div>
                          <Label htmlFor="tile-color">Tile Color</Label>
                          <div className="flex gap-2 mt-2">
                            <Input
                              id="tile-color"
                              type="color"
                              value={newTheme.tileColor}
                              onChange={(e) => setNewTheme({...newTheme, tileColor: e.target.value})}
                              className="w-20 h-10"
                            />
                            <Input
                              value={newTheme.tileColor}
                              onChange={(e) => setNewTheme({...newTheme, tileColor: e.target.value})}
                              className="flex-1"
                            />
                          </div>
                        </div>
                        <div>
                          <Label htmlFor="text-color">Text Color</Label>
                          <div className="flex gap-2 mt-2">
                            <Input
                              id="text-color"
                              type="color"
                              value={newTheme.textColor}
                              onChange={(e) => setNewTheme({...newTheme, textColor: e.target.value})}
                              className="w-20 h-10"
                            />
                            <Input
                              value={newTheme.textColor}
                              onChange={(e) => setNewTheme({...newTheme, textColor: e.target.value})}
                              className="flex-1"
                            />
                          </div>
                        </div>
                        <div>
                          <Label htmlFor="button-color">Button Color</Label>
                          <div className="flex gap-2 mt-2">
                            <Input
                              id="button-color"
                              type="color"
                              value={newTheme.buttonColor}
                              onChange={(e) => setNewTheme({...newTheme, buttonColor: e.target.value})}
                              className="w-20 h-10"
                            />
                            <Input
                              value={newTheme.buttonColor}
                              onChange={(e) => setNewTheme({...newTheme, buttonColor: e.target.value})}
                              className="flex-1"
                            />
                          </div>
                        </div>
                        <Button onClick={createTheme} className="w-full">Save Theme</Button>
                      </div>
                    </DialogContent>
                  </Dialog>
                </div>
              </CardHeader>
              <CardContent>
                <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-4">
                  {themes.map(theme => (
                    <div
                      key={theme.id}
                      className="border rounded-lg p-4 cursor-pointer transition-all hover:shadow-lg"
                      style={{ 
                        backgroundColor: theme.tileColor,
                        borderColor: currentTheme.id === theme.id ? currentTheme.buttonColor : 'transparent',
                        borderWidth: currentTheme.id === theme.id ? '2px' : '1px'
                      }}
                      onClick={() => setCurrentTheme(theme)}
                    >
                      <div className="flex justify-between items-start mb-3">
                        <h3 className="font-semibold" style={{ color: theme.textColor }}>{theme.name}</h3>
                        {theme.id !== 1 && (
                          <Button
                            variant="ghost"
                            size="sm"
                            onClick={(e) => {
                              e.stopPropagation();
                              deleteTheme(theme.id);
                            }}
                            className="h-6 w-6 p-0"
                          >
                            ×
                          </Button>
                        )}
                      </div>
                      <div className="grid grid-cols-4 gap-2">
                        <div className="aspect-square rounded" style={{ backgroundColor: theme.bgColor }} title="Background" />
                        <div className="aspect-square rounded" style={{ backgroundColor: theme.tileColor }} title="Tile" />
                        <div className="aspect-square rounded" style={{ backgroundColor: theme.textColor }} title="Text" />
                        <div className="aspect-square rounded" style={{ backgroundColor: theme.buttonColor }} title="Button" />
                      </div>
                      {currentTheme.id === theme.id && (
                        <div className="mt-2 text-sm font-semibold text-center" style={{ color: theme.buttonColor }}>
                          Active
                        </div>
                      )}
                    </div>
                  ))}
                </div>
              </CardContent>
            </Card>

            <p className="text-sm text-center mt-8 opacity-60">Type "exit" to return to games</p>
          </div>
        </div>
      </div>
    );
  }

  if (mode === 'calculator') {
    return (
      <div className="container py-8">
        <div className="content max-w-md mx-auto">
          <Card>
            <CardHeader>
              <CardTitle className="text-center">{pageTitle}</CardTitle>
            </CardHeader>
            <CardContent>
              <div className="bg-muted p-4 rounded-lg mb-4 text-right text-2xl font-mono min-h-[60px] flex items-center justify-end">
                {calcDisplay}
              </div>
              <div className="grid grid-cols-4 gap-2">
                {['7', '8', '9', '/'].map(btn => (
                  <Button key={btn} onClick={() => handleCalcInput(btn)} variant="outline">{btn}</Button>
                ))}
                {['4', '5', '6', '*'].map(btn => (
                  <Button key={btn} onClick={() => handleCalcInput(btn)} variant="outline">{btn}</Button>
                ))}
                {['1', '2', '3', '-'].map(btn => (
                  <Button key={btn} onClick={() => handleCalcInput(btn)} variant="outline">{btn}</Button>
                ))}
                {['0', '.', '=', '+'].map(btn => (
                  <Button 
                    key={btn} 
                    onClick={() => btn === '=' ? calculateResult() : handleCalcInput(btn)} 
                    variant={btn === '=' ? 'default' : 'outline'}
                  >
                    {btn}
                  </Button>
                ))}
                <Button onClick={clearCalc} variant="destructive" className="col-span-4">Clear</Button>
              </div>
            </CardContent>
          </Card>
        </div>
      </div>
    );
  }

  if (selectedGame) {
    return (
      <div style={{ backgroundColor: currentTheme.bgColor, minHeight: '100vh' }}>
        {panicButton}
        <div className="container py-4">
          <div className="content">
            <Button onClick={() => setSelectedGame(null)} variant="outline" className="mb-4" style={{ color: currentTheme.textColor, borderColor: currentTheme.textColor }}>
              ← Back to Games
            </Button>
            <div style={{ color: currentTheme.textColor }}>
              {selectedGame === 'snake' && <SnakeGame theme={currentTheme} />}
              {selectedGame === '2048' && <Game2048 theme={currentTheme} />}
              {selectedGame === 'memory' && <MemoryGame theme={currentTheme} />}
              {selectedGame === 'breakout' && <BreakoutGame theme={currentTheme} />}
              {selectedGame === 'tictactoe' && <TicTacToe theme={currentTheme} />}
              {selectedGame === 'flappy' && <FlappyBird theme={currentTheme} />}
              {selectedGame === 'pong' && <PongGame theme={currentTheme} />}
              {selectedGame === 'invaders' && <SpaceInvaders theme={currentTheme} />}
              {selectedGame === 'doodle' && <DoodleJump theme={currentTheme} />}
              {selectedGame === 'tetris' && <TetrisGame theme={currentTheme} />}
              {selectedGame === 'simon' && <SimonGame theme={currentTheme} />}
              {selectedGame === 'whack' && <WhackAMole theme={currentTheme} />}
              {selectedGame === 'crossy' && <CrossyRoad theme={currentTheme} />}
            </div>
          </div>
        </div>
      </div>
    );
  }

  // Website offline state
  if (!websiteEnabled) {
    return (
      <div style={{ backgroundColor: currentTheme.bgColor, minHeight: '100vh' }}>
        {panicButton}
        <div className="container py-16">
          <div className="content max-w-2xl mx-auto text-center">
            <h1 className="font-heading text-5xl mb-4" style={{ color: currentTheme.textColor }}>Games Unavailable</h1>
            <p className="text-xl" style={{ color: currentTheme.textColor, opacity: 0.8 }}>{offlineMessage}</p>
          </div>
        </div>
      </div>
    );
  }

  return (
    <div style={{ backgroundColor: currentTheme.bgColor, minHeight: '100vh' }}>
      {panicButton}
      <div className="container py-8">
        <div className="content">
          <h1 className="font-heading text-4xl mb-2 text-center" style={{ color: currentTheme.textColor }}>NexusPlay</h1>
          <p className="text-center mb-8" style={{ color: currentTheme.textColor, opacity: 0.7 }}>Choose a game to play</p>
          <div className="grid md:grid-cols-3 lg:grid-cols-4 gap-6 max-w-6xl mx-auto">
            <GameCard 
              title="Snake" 
              description="Classic arcade game. Use arrow keys to control."
              onClick={() => setSelectedGame('snake')}
              theme={currentTheme}
            />
            <GameCard 
              title="2048" 
              description="Combine tiles to reach 2048!"
              onClick={() => setSelectedGame('2048')}
              theme={currentTheme}
            />
            <GameCard 
              title="Memory Match" 
              description="Find matching pairs of cards."
              onClick={() => setSelectedGame('memory')}
              theme={currentTheme}
            />
            <GameCard 
              title="Breakout" 
              description="Break all the bricks with the ball!"
              onClick={() => setSelectedGame('breakout')}
              theme={currentTheme}
            />
            <GameCard 
              title="Tic Tac Toe" 
              description="Classic strategy game for two players."
              onClick={() => setSelectedGame('tictactoe')}
              theme={currentTheme}
            />
            <GameCard 
              title="Flappy Bird" 
              description="Tap to fly through the pipes!"
              onClick={() => setSelectedGame('flappy')}
              theme={currentTheme}
            />
            <GameCard 
              title="Pong" 
              description="Classic two-player paddle game."
              onClick={() => setSelectedGame('pong')}
              theme={currentTheme}
            />
            <GameCard 
              title="Space Invaders" 
              description="Shoot down the alien invaders!"
              onClick={() => setSelectedGame('invaders')}
              theme={currentTheme}
            />
            <GameCard 
              title="Doodle Jump" 
              description="Jump higher on platforms!"
              onClick={() => setSelectedGame('doodle')}
              theme={currentTheme}
            />
            <GameCard 
              title="Tetris" 
              description="Stack blocks to clear lines!"
              onClick={() => setSelectedGame('tetris')}
              theme={currentTheme}
            />
            <GameCard 
              title="Simon Says" 
              description="Remember and repeat the pattern!"
              onClick={() => setSelectedGame('simon')}
              theme={currentTheme}
            />
            <GameCard 
              title="Whack-a-Mole" 
              description="Hit the moles as fast as you can!"
              onClick={() => setSelectedGame('whack')}
              theme={currentTheme}
            />
            <GameCard 
              title="Crossy Road" 
              description="Cross the road without getting hit!"
              onClick={() => setSelectedGame('crossy')}
              theme={currentTheme}
            />
          </div>
        </div>
      </div>
    </div>
  );
}

function GameCard({ title, description, onClick, theme }) {
  return (
    <Card 
      className="cursor-pointer hover:shadow-lg transition-shadow" 
      onClick={onClick}
      style={{ backgroundColor: theme.tileColor, color: theme.textColor, borderColor: theme.textColor + '20' }}
    >
      <CardHeader>
        <CardTitle>{title}</CardTitle>
      </CardHeader>
      <CardContent>
        <p className="text-sm" style={{ opacity: 0.8 }}>{description}</p>
      </CardContent>
    </Card>
  );
}

// Game components remain the same but accept theme prop
function SnakeGame({ theme }) {
  const [snake, setSnake] = useState([[10, 10]]);
  const [food, setFood] = useState([15, 15]);
  const [direction, setDirection] = useState('RIGHT');
  const [gameOver, setGameOver] = useState(false);
  const [score, setScore] = useState(0);
  const gridSize = 20;

  useEffect(() => {
    if (gameOver) return;

    const handleKeyPress = (e) => {
      if (e.key === 'ArrowUp' && direction !== 'DOWN') setDirection('UP');
      if (e.key === 'ArrowDown' && direction !== 'UP') setDirection('DOWN');
      if (e.key === 'ArrowLeft' && direction !== 'RIGHT') setDirection('LEFT');
      if (e.key === 'ArrowRight' && direction !== 'LEFT') setDirection('RIGHT');
    };

    window.addEventListener('keydown', handleKeyPress);
    return () => window.removeEventListener('keydown', handleKeyPress);
  }, [direction, gameOver]);

  useEffect(() => {
    if (gameOver) return;

    const moveSnake = setInterval(() => {
      setSnake(prev => {
        const head = prev[0];
        let newHead;

        switch(direction) {
          case 'UP': newHead = [head[0], head[1] - 1]; break;
          case 'DOWN': newHead = [head[0], head[1] + 1]; break;
          case 'LEFT': newHead = [head[0] - 1, head[1]]; break;
          case 'RIGHT': newHead = [head[0] + 1, head[1]]; break;
          default: newHead = head;
        }

        if (newHead[0] < 0 || newHead[0] >= gridSize || newHead[1] < 0 || newHead[1] >= gridSize) {
          setGameOver(true);
          return prev;
        }

        if (prev.some(segment => segment[0] === newHead[0] && segment[1] === newHead[1])) {
          setGameOver(true);
          return prev;
        }

        const newSnake = [newHead, ...prev];

        if (newHead[0] === food[0] && newHead[1] === food[1]) {
          setScore(s => s + 10);
          setFood([Math.floor(Math.random() * gridSize), Math.floor(Math.random() * gridSize)]);
        } else {
          newSnake.pop();
        }

        return newSnake;
      });
    }, 150);

    return () => clearInterval(moveSnake);
  }, [direction, food, gameOver]);

  const resetGame = () => {
    setSnake([[10, 10]]);
    setFood([15, 15]);
    setDirection('RIGHT');
    setGameOver(false);
    setScore(0);
  };

  return (
    <div className="max-w-2xl mx-auto">
      <div className="flex justify-between items-center mb-4">
        <h2 className="font-heading text-2xl">Snake</h2>
        <div className="text-xl">Score: {score}</div>
      </div>
      <div className="border rounded-lg p-4 inline-block" style={{ backgroundColor: theme.tileColor, borderColor: theme.textColor + '20' }}>
        <div style={{ display: 'grid', gridTemplateColumns: `repeat(${gridSize}, 20px)`, gap: '1px' }}>
          {Array.from({ length: gridSize * gridSize }).map((_, i) => {
            const x = i % gridSize;
            const y = Math.floor(i / gridSize);
            const isSnake = snake.some(s => s[0] === x && s[1] === y);
            const isFood = food[0] === x && food[1] === y;
            return (
              <div
                key={i}
                style={{
                  width: '20px',
                  height: '20px',
                  backgroundColor: isSnake ? theme.buttonColor : isFood ? '#ef4444' : theme.bgColor,
                  borderRadius: '2px'
                }}
              />
            );
          })}
        </div>
      </div>
      {gameOver && (
        <div className="mt-4 text-center">
          <p className="text-xl mb-4">Game Over! Final Score: {score}</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Use arrow keys to control the snake</p>
    </div>
  );
}

// Include all other game components with theme support...
// (For brevity, I'm including just the structure - the full code would include all 10 games with theme props)

function Game2048({ theme }) {
  const [grid, setGrid] = useState(() => {
    const newGrid = Array(4).fill(null).map(() => Array(4).fill(0));
    addRandomTile(newGrid);
    addRandomTile(newGrid);
    return newGrid;
  });
  const [score, setScore] = useState(0);
  const [gameOver, setGameOver] = useState(false);

  function addRandomTile(grid) {
    const emptyCells = [];
    for (let i = 0; i < 4; i++) {
      for (let j = 0; j < 4; j++) {
        if (grid[i][j] === 0) emptyCells.push([i, j]);
      }
    }
    if (emptyCells.length > 0) {
      const [row, col] = emptyCells[Math.floor(Math.random() * emptyCells.length)];
      grid[row][col] = Math.random() < 0.9 ? 2 : 4;
    }
  }

  useEffect(() => {
    const handleKeyPress = (e) => {
      if (gameOver) return;
      let moved = false;
      let newGrid = grid.map(row => [...row]);

      if (e.key === 'ArrowUp') moved = moveUp(newGrid);
      if (e.key === 'ArrowDown') moved = moveDown(newGrid);
      if (e.key === 'ArrowLeft') moved = moveLeft(newGrid);
      if (e.key === 'ArrowRight') moved = moveRight(newGrid);

      if (moved) {
        addRandomTile(newGrid);
        setGrid(newGrid);
        if (!canMove(newGrid)) setGameOver(true);
      }
    };

    window.addEventListener('keydown', handleKeyPress);
    return () => window.removeEventListener('keydown', handleKeyPress);
  }, [grid, gameOver]);

  function moveLeft(grid) {
    let moved = false;
    for (let i = 0; i < 4; i++) {
      let row = grid[i].filter(val => val !== 0);
      for (let j = 0; j < row.length - 1; j++) {
        if (row[j] === row[j + 1]) {
          row[j] *= 2;
          setScore(s => s + row[j]);
          row.splice(j + 1, 1);
          moved = true;
        }
      }
      while (row.length < 4) row.push(0);
      if (JSON.stringify(row) !== JSON.stringify(grid[i])) moved = true;
      grid[i] = row;
    }
    return moved;
  }

  function moveRight(grid) {
    for (let i = 0; i < 4; i++) grid[i].reverse();
    const moved = moveLeft(grid);
    for (let i = 0; i < 4; i++) grid[i].reverse();
    return moved;
  }

  function moveUp(grid) {
    transpose(grid);
    const moved = moveLeft(grid);
    transpose(grid);
    return moved;
  }

  function moveDown(grid) {
    transpose(grid);
    const moved = moveRight(grid);
    transpose(grid);
    return moved;
  }

  function transpose(grid) {
    for (let i = 0; i < 4; i++) {
      for (let j = i + 1; j < 4; j++) {
        [grid[i][j], grid[j][i]] = [grid[j][i], grid[i][j]];
      }
    }
  }

  function canMove(grid) {
    for (let i = 0; i < 4; i++) {
      for (let j = 0; j < 4; j++) {
        if (grid[i][j] === 0) return true;
        if (j < 3 && grid[i][j] === grid[i][j + 1]) return true;
        if (i < 3 && grid[i][j] === grid[i + 1][j]) return true;
      }
    }
    return false;
  }

  const resetGame = () => {
    const newGrid = Array(4).fill(null).map(() => Array(4).fill(0));
    addRandomTile(newGrid);
    addRandomTile(newGrid);
    setGrid(newGrid);
    setScore(0);
    setGameOver(false);
  };

  const getTileColor = (value) => {
    const colors = {
      0: theme.bgColor,
      2: '#eee4da',
      4: '#ede0c8',
      8: '#f2b179',
      16: '#f59563',
      32: '#f67c5f',
      64: '#f65e3b',
      128: '#edcf72',
      256: '#edcc61',
      512: '#edc850',
      1024: '#edc53f',
      2048: '#edc22e'
    };
    return colors[value] || '#3c3a32';
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">2048</h2>
      <div className="text-xl mb-4">Score: {score}</div>
      <div className="inline-block p-4" style={{ backgroundColor: theme.tileColor, borderRadius: '0.5rem' }}>
        <div className="grid grid-cols-4 gap-2">
          {grid.map((row, i) => row.map((cell, j) => (
            <div
              key={`${i}-${j}`}
              className="w-20 h-20 flex items-center justify-center text-2xl font-bold rounded"
              style={{ backgroundColor: getTileColor(cell), color: cell > 4 ? '#f9f6f2' : '#776e65' }}
            >
              {cell !== 0 ? cell : ''}
            </div>
          )))}
        </div>
      </div>
      {gameOver && (
        <div className="mt-4">
          <p className="text-xl mb-4">Game Over! Final Score: {score}</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Use arrow keys to play</p>
    </div>
  );
}

function MemoryGame({ theme }) {
  const [cards, setCards] = useState([]);
  const [flipped, setFlipped] = useState([]);
  const [matched, setMatched] = useState([]);
  const [moves, setMoves] = useState(0);
  const emojis = ['🎮', '🎯', '🎲', '🎪', '🎨', '🎭', '🎸', '🎺'];

  useEffect(() => {
    const shuffled = [...emojis, ...emojis]
      .sort(() => Math.random() - 0.5)
      .map((emoji, i) => ({ id: i, emoji }));
    setCards(shuffled);
  }, []);

  const handleClick = (id) => {
    if (flipped.length === 2 || flipped.includes(id) || matched.includes(id)) return;
    
    const newFlipped = [...flipped, id];
    setFlipped(newFlipped);

    if (newFlipped.length === 2) {
      setMoves(moves + 1);
      const [first, second] = newFlipped;
      if (cards[first].emoji === cards[second].emoji) {
        setMatched([...matched, first, second]);
        setFlipped([]);
      } else {
        setTimeout(() => setFlipped([]), 1000);
      }
    }
  };

  const resetGame = () => {
    const shuffled = [...emojis, ...emojis]
      .sort(() => Math.random() - 0.5)
      .map((emoji, i) => ({ id: i, emoji }));
    setCards(shuffled);
    setFlipped([]);
    setMatched([]);
    setMoves(0);
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Memory Match</h2>
      <div className="text-xl mb-4">Moves: {moves}</div>
      <div className="grid grid-cols-4 gap-4 max-w-md mx-auto mb-4">
        {cards.map((card) => (
          <button
            key={card.id}
            onClick={() => handleClick(card.id)}
            className="aspect-square rounded-lg text-4xl flex items-center justify-center transition-all"
            style={{
              backgroundColor: flipped.includes(card.id) || matched.includes(card.id) ? theme.buttonColor : theme.tileColor,
              border: `2px solid ${theme.textColor}20`,
              cursor: matched.includes(card.id) ? 'default' : 'pointer'
            }}
          >
            {flipped.includes(card.id) || matched.includes(card.id) ? card.emoji : '?'}
          </button>
        ))}
      </div>
      {matched.length === cards.length && cards.length > 0 && (
        <div className="mt-4">
          <p className="text-xl mb-4">You won in {moves} moves!</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
    </div>
  );
}

function BreakoutGame({ theme }) {
  const canvasRef = useRef(null);
  const [score, setScore] = useState(0);
  const [gameOver, setGameOver] = useState(false);
  const [gameWon, setGameWon] = useState(false);

  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    
    let paddle = { x: 160, y: 380, width: 80, height: 10, speed: 7 };
    let ball = { x: 200, y: 300, dx: 3, dy: -3, radius: 8 };
    let bricks = [];
    const brickRowCount = 5;
    const brickColumnCount = 8;
    const brickWidth = 45;
    const brickHeight = 15;
    const brickPadding = 5;
    const brickOffsetTop = 30;
    const brickOffsetLeft = 10;

    for (let c = 0; c < brickColumnCount; c++) {
      bricks[c] = [];
      for (let r = 0; r < brickRowCount; r++) {
        bricks[c][r] = { x: 0, y: 0, status: 1 };
      }
    }

    let rightPressed = false;
    let leftPressed = false;

    const keyDownHandler = (e) => {
      if (e.key === 'Right' || e.key === 'ArrowRight') rightPressed = true;
      if (e.key === 'Left' || e.key === 'ArrowLeft') leftPressed = true;
    };

    const keyUpHandler = (e) => {
      if (e.key === 'Right' || e.key === 'ArrowRight') rightPressed = false;
      if (e.key === 'Left' || e.key === 'ArrowLeft') leftPressed = false;
    };

    document.addEventListener('keydown', keyDownHandler);
    document.addEventListener('keyup', keyUpHandler);

    function drawBall() {
      ctx.beginPath();
      ctx.arc(ball.x, ball.y, ball.radius, 0, Math.PI * 2);
      ctx.fillStyle = theme.buttonColor;
      ctx.fill();
      ctx.closePath();
    }

    function drawPaddle() {
      ctx.beginPath();
      ctx.rect(paddle.x, paddle.y, paddle.width, paddle.height);
      ctx.fillStyle = theme.buttonColor;
      ctx.fill();
      ctx.closePath();
    }

    function drawBricks() {
      for (let c = 0; c < brickColumnCount; c++) {
        for (let r = 0; r < brickRowCount; r++) {
          if (bricks[c][r].status === 1) {
            const brickX = c * (brickWidth + brickPadding) + brickOffsetLeft;
            const brickY = r * (brickHeight + brickPadding) + brickOffsetTop;
            bricks[c][r].x = brickX;
            bricks[c][r].y = brickY;
            ctx.beginPath();
            ctx.rect(brickX, brickY, brickWidth, brickHeight);
            ctx.fillStyle = theme.buttonColor;
            ctx.fill();
            ctx.closePath();
          }
        }
      }
    }

    function collisionDetection() {
      for (let c = 0; c < brickColumnCount; c++) {
        for (let r = 0; r < brickRowCount; r++) {
          const b = bricks[c][r];
          if (b.status === 1) {
            if (ball.x > b.x && ball.x < b.x + brickWidth && ball.y > b.y && ball.y < b.y + brickHeight) {
              ball.dy = -ball.dy;
              b.status = 0;
              setScore(s => s + 10);
              if (bricks.flat().every(brick => brick.status === 0)) {
                setGameWon(true);
              }
            }
          }
        }
      }
    }

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      drawBricks();
      drawBall();
      drawPaddle();
      collisionDetection();

      if (ball.x + ball.dx > canvas.width - ball.radius || ball.x + ball.dx < ball.radius) {
        ball.dx = -ball.dx;
      }
      if (ball.y + ball.dy < ball.radius) {
        ball.dy = -ball.dy;
      } else if (ball.y + ball.dy > canvas.height - ball.radius) {
        if (ball.x > paddle.x && ball.x < paddle.x + paddle.width) {
          ball.dy = -ball.dy;
        } else {
          setGameOver(true);
          return;
        }
      }

      if (rightPressed && paddle.x < canvas.width - paddle.width) {
        paddle.x += paddle.speed;
      } else if (leftPressed && paddle.x > 0) {
        paddle.x -= paddle.speed;
      }

      ball.x += ball.dx;
      ball.y += ball.dy;

      if (!gameOver && !gameWon) {
        requestAnimationFrame(draw);
      }
    }

    draw();

    return () => {
      document.removeEventListener('keydown', keyDownHandler);
      document.removeEventListener('keyup', keyUpHandler);
    };
  }, [gameOver, gameWon, theme]);

  const resetGame = () => {
    setScore(0);
    setGameOver(false);
    setGameWon(false);
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Breakout</h2>
      <div className="text-xl mb-4">Score: {score}</div>
      <canvas ref={canvasRef} width="400" height="400" className="border rounded" style={{ backgroundColor: theme.bgColor, borderColor: theme.textColor + '20' }} />
      {(gameOver || gameWon) && (
        <div className="mt-4">
          <p className="text-xl mb-4">{gameWon ? `You Won! Score: ${score}` : `Game Over! Score: ${score}`}</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Use arrow keys to move the paddle</p>
    </div>
  );
}

function TicTacToe({ theme }) {
  const [board, setBoard] = useState(Array(9).fill(null));
  const [isXNext, setIsXNext] = useState(true);
  const [winner, setWinner] = useState(null);

  const calculateWinner = (squares) => {
    const lines = [
      [0, 1, 2], [3, 4, 5], [6, 7, 8],
      [0, 3, 6], [1, 4, 7], [2, 5, 8],
      [0, 4, 8], [2, 4, 6]
    ];
    for (let [a, b, c] of lines) {
      if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
        return squares[a];
      }
    }
    return null;
  };

  const handleClick = (i) => {
    if (board[i] || winner) return;
    const newBoard = [...board];
    newBoard[i] = isXNext ? 'X' : 'O';
    setBoard(newBoard);
    setIsXNext(!isXNext);
    const gameWinner = calculateWinner(newBoard);
    if (gameWinner) setWinner(gameWinner);
  };

  const resetGame = () => {
    setBoard(Array(9).fill(null));
    setIsXNext(true);
    setWinner(null);
  };

  const isDraw = !winner && board.every(cell => cell !== null);

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Tic Tac Toe</h2>
      <div className="text-xl mb-4">
        {winner ? `Winner: ${winner}` : isDraw ? "It's a Draw!" : `Next: ${isXNext ? 'X' : 'O'}`}
      </div>
      <div className="inline-block">
        <div className="grid grid-cols-3 gap-2">
          {board.map((cell, i) => (
            <button
              key={i}
              onClick={() => handleClick(i)}
              className="w-24 h-24 text-4xl font-bold rounded transition-all"
              style={{
                backgroundColor: theme.tileColor,
                border: `2px solid ${theme.textColor}20`,
                color: theme.textColor,
                cursor: cell || winner ? 'default' : 'pointer'
              }}
            >
              {cell}
            </button>
          ))}
        </div>
      </div>
      {(winner || isDraw) && (
        <div className="mt-4">
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
    </div>
  );
}

function FlappyBird({ theme }) {
  const canvasRef = useRef(null);
  const [score, setScore] = useState(0);
  const [gameOver, setGameOver] = useState(false);
  const [gameStarted, setGameStarted] = useState(false);

  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas || !gameStarted) return;
    const ctx = canvas.getContext('2d');

    let bird = { x: 50, y: 150, velocity: 0, gravity: 0.5, jump: -8 };
    let pipes = [{ x: 400, top: 100, gap: 120 }];
    let frameCount = 0;

    const handleSpace = (e) => {
      if (e.code === 'Space' && !gameOver) {
        bird.velocity = bird.jump;
      }
    };

    document.addEventListener('keydown', handleSpace);

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      // Draw bird
      ctx.beginPath();
      ctx.arc(bird.x, bird.y, 15, 0, Math.PI * 2);
      ctx.fillStyle = theme.buttonColor;
      ctx.fill();
      ctx.closePath();

      // Draw pipes
      ctx.fillStyle = theme.buttonColor;
      pipes.forEach(pipe => {
        ctx.fillRect(pipe.x, 0, 50, pipe.top);
        ctx.fillRect(pipe.x, pipe.top + pipe.gap, 50, canvas.height - pipe.top - pipe.gap);
      });

      // Update bird
      bird.velocity += bird.gravity;
      bird.y += bird.velocity;

      // Update pipes
      pipes.forEach(pipe => {
        pipe.x -= 2;
        if (pipe.x + 50 < 0) {
          pipe.x = 400;
          pipe.top = Math.random() * 150 + 50;
          setScore(s => s + 1);
        }

        // Collision detection
        if (bird.x + 15 > pipe.x && bird.x - 15 < pipe.x + 50) {
          if (bird.y - 15 < pipe.top || bird.y + 15 > pipe.top + pipe.gap) {
            setGameOver(true);
          }
        }
      });

      // Check boundaries
      if (bird.y + 15 > canvas.height || bird.y - 15 < 0) {
        setGameOver(true);
      }

      frameCount++;
      if (frameCount % 150 === 0) {
        pipes.push({ x: 400, top: Math.random() * 150 + 50, gap: 120 });
      }

      if (!gameOver) {
        requestAnimationFrame(draw);
      }
    }

    draw();

    return () => {
      document.removeEventListener('keydown', handleSpace);
    };
  }, [gameStarted, gameOver, theme]);

  const resetGame = () => {
    setScore(0);
    setGameOver(false);
    setGameStarted(true);
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Flappy Bird</h2>
      <div className="text-xl mb-4">Score: {score}</div>
      <canvas ref={canvasRef} width="400" height="400" className="border rounded" style={{ backgroundColor: theme.bgColor, borderColor: theme.textColor + '20' }} />
      {!gameStarted && (
        <div className="mt-4">
          <Button onClick={() => setGameStarted(true)} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Start Game</Button>
        </div>
      )}
      {gameOver && (
        <div className="mt-4">
          <p className="text-xl mb-4">Game Over! Score: {score}</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Press SPACE to jump</p>
    </div>
  );
}

function PongGame({ theme }) {
  const canvasRef = useRef(null);
  const [score, setScore] = useState({ player: 0, ai: 0 });
  const [gameStarted, setGameStarted] = useState(false);

  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas || !gameStarted) return;
    const ctx = canvas.getContext('2d');

    let paddle1 = { x: 10, y: 150, width: 10, height: 60, speed: 5 };
    let paddle2 = { x: 380, y: 150, width: 10, height: 60, speed: 3 };
    let ball = { x: 200, y: 200, dx: 3, dy: 3, radius: 8 };

    let upPressed = false;
    let downPressed = false;

    const keyDownHandler = (e) => {
      if (e.key === 'ArrowUp') upPressed = true;
      if (e.key === 'ArrowDown') downPressed = true;
    };

    const keyUpHandler = (e) => {
      if (e.key === 'ArrowUp') upPressed = false;
      if (e.key === 'ArrowDown') downPressed = false;
    };

    document.addEventListener('keydown', keyDownHandler);
    document.addEventListener('keyup', keyUpHandler);

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      // Draw paddles
      ctx.fillStyle = theme.buttonColor;
      ctx.fillRect(paddle1.x, paddle1.y, paddle1.width, paddle1.height);
      ctx.fillRect(paddle2.x, paddle2.y, paddle2.width, paddle2.height);

      // Draw ball
      ctx.beginPath();
      ctx.arc(ball.x, ball.y, ball.radius, 0, Math.PI * 2);
      ctx.fillStyle = theme.buttonColor;
      ctx.fill();
      ctx.closePath();

      // Move ball
      ball.x += ball.dx;
      ball.y += ball.dy;

      // Ball collision with top/bottom
      if (ball.y + ball.radius > canvas.height || ball.y - ball.radius < 0) {
        ball.dy = -ball.dy;
      }

      // Ball collision with paddles
      if (ball.x - ball.radius < paddle1.x + paddle1.width && ball.y > paddle1.y && ball.y < paddle1.y + paddle1.height) {
        ball.dx = -ball.dx;
      }
      if (ball.x + ball.radius > paddle2.x && ball.y > paddle2.y && ball.y < paddle2.y + paddle2.height) {
        ball.dx = -ball.dx;
      }

      // Score
      if (ball.x < 0) {
        setScore(s => ({ ...s, ai: s.ai + 1 }));
        ball.x = 200;
        ball.y = 200;
      }
      if (ball.x > canvas.width) {
        setScore(s => ({ ...s, player: s.player + 1 }));
        ball.x = 200;
        ball.y = 200;
      }

      // Move player paddle
      if (upPressed && paddle1.y > 0) paddle1.y -= paddle1.speed;
      if (downPressed && paddle1.y < canvas.height - paddle1.height) paddle1.y += paddle1.speed;

      // AI paddle
      if (ball.y < paddle2.y + paddle2.height / 2) paddle2.y -= paddle2.speed;
      if (ball.y > paddle2.y + paddle2.height / 2) paddle2.y += paddle2.speed;

      requestAnimationFrame(draw);
    }

    draw();

    return () => {
      document.removeEventListener('keydown', keyDownHandler);
      document.removeEventListener('keyup', keyUpHandler);
    };
  }, [gameStarted, theme]);

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Pong</h2>
      <div className="text-xl mb-4">Player: {score.player} | AI: {score.ai}</div>
      <canvas ref={canvasRef} width="400" height="400" className="border rounded" style={{ backgroundColor: theme.bgColor, borderColor: theme.textColor + '20' }} />
      {!gameStarted && (
        <div className="mt-4">
          <Button onClick={() => setGameStarted(true)} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Start Game</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Use arrow keys to move your paddle</p>
    </div>
  );
}

function SpaceInvaders({ theme }) {
  const canvasRef = useRef(null);
  const [score, setScore] = useState(0);
  const [gameOver, setGameOver] = useState(false);
  const [gameStarted, setGameStarted] = useState(false);

  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas || !gameStarted) return;
    const ctx = canvas.getContext('2d');

    let player = { x: 180, y: 360, width: 40, height: 20, speed: 5 };
    let bullets = [];
    let aliens = [];
    let alienBullets = [];

    for (let row = 0; row < 3; row++) {
      for (let col = 0; col < 8; col++) {
        aliens.push({ x: col * 50 + 10, y: row * 40 + 30, width: 30, height: 20, alive: true });
      }
    }

    let leftPressed = false;
    let rightPressed = false;
    let spacePressed = false;
    let lastShot = 0;

    const keyDownHandler = (e) => {
      if (e.key === 'ArrowLeft') leftPressed = true;
      if (e.key === 'ArrowRight') rightPressed = true;
      if (e.code === 'Space') spacePressed = true;
    };

    const keyUpHandler = (e) => {
      if (e.key === 'ArrowLeft') leftPressed = false;
      if (e.key === 'ArrowRight') rightPressed = false;
      if (e.code === 'Space') spacePressed = false;
    };

    document.addEventListener('keydown', keyDownHandler);
    document.addEventListener('keyup', keyUpHandler);

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      // Draw player
      ctx.fillStyle = theme.buttonColor;
      ctx.fillRect(player.x, player.y, player.width, player.height);

      // Draw aliens
      aliens.forEach(alien => {
        if (alien.alive) {
          ctx.fillStyle = theme.buttonColor;
          ctx.fillRect(alien.x, alien.y, alien.width, alien.height);
        }
      });

      // Draw bullets
      ctx.fillStyle = theme.buttonColor;
      bullets.forEach(bullet => {
        ctx.fillRect(bullet.x, bullet.y, 3, 10);
      });

      alienBullets.forEach(bullet => {
        ctx.fillRect(bullet.x, bullet.y, 3, 10);
      });

      // Move player
      if (leftPressed && player.x > 0) player.x -= player.speed;
      if (rightPressed && player.x < canvas.width - player.width) player.x += player.speed;

      // Shoot
      const now = Date.now();
      if (spacePressed && now - lastShot > 300) {
        bullets.push({ x: player.x + player.width / 2, y: player.y });
        lastShot = now;
      }

      // Move bullets
      bullets = bullets.filter(bullet => {
        bullet.y -= 5;
        return bullet.y > 0;
      });

      alienBullets = alienBullets.filter(bullet => {
        bullet.y += 3;
        if (bullet.y > player.y && bullet.y < player.y + player.height && bullet.x > player.x && bullet.x < player.x + player.width) {
          setGameOver(true);
        }
        return bullet.y < canvas.height;
      });

      // Collision detection
      bullets.forEach(bullet => {
        aliens.forEach(alien => {
          if (alien.alive && bullet.x > alien.x && bullet.x < alien.x + alien.width && bullet.y > alien.y && bullet.y < alien.y + alien.height) {
            alien.alive = false;
            bullet.y = -10;
            setScore(s => s + 10);
          }
        });
      });

      // Alien shooting
      if (Math.random() < 0.01) {
        const aliveAliens = aliens.filter(a => a.alive);
        if (aliveAliens.length > 0) {
          const shooter = aliveAliens[Math.floor(Math.random() * aliveAliens.length)];
          alienBullets.push({ x: shooter.x + shooter.width / 2, y: shooter.y + shooter.height });
        }
      }

      if (!gameOver && aliens.some(a => a.alive)) {
        requestAnimationFrame(draw);
      } else if (!aliens.some(a => a.alive)) {
        setGameOver(true);
      }
    }

    draw();

    return () => {
      document.removeEventListener('keydown', keyDownHandler);
      document.removeEventListener('keyup', keyUpHandler);
    };
  }, [gameStarted, gameOver, theme]);

  const resetGame = () => {
    setScore(0);
    setGameOver(false);
    setGameStarted(true);
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Space Invaders</h2>
      <div className="text-xl mb-4">Score: {score}</div>
      <canvas ref={canvasRef} width="400" height="400" className="border rounded" style={{ backgroundColor: theme.bgColor, borderColor: theme.textColor + '20' }} />
      {!gameStarted && (
        <div className="mt-4">
          <Button onClick={() => setGameStarted(true)} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Start Game</Button>
        </div>
      )}
      {gameOver && (
        <div className="mt-4">
          <p className="text-xl mb-4">Game Over! Score: {score}</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Arrow keys to move, SPACE to shoot</p>
    </div>
  );
}

function DoodleJump({ theme }) {
  const canvasRef = useRef(null);
  const [score, setScore] = useState(0);
  const [gameOver, setGameOver] = useState(false);
  const [gameStarted, setGameStarted] = useState(false);

  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas || !gameStarted) return;
    const ctx = canvas.getContext('2d');

    let player = { x: 200, y: 300, width: 30, height: 30, velocityY: 0, velocityX: 0 };
    let platforms = [];
    let gravity = 0.3;
    let jumpPower = -10;
    let cameraY = 0;

    for (let i = 0; i < 10; i++) {
      platforms.push({ x: Math.random() * 340, y: i * 50, width: 60, height: 10 });
    }

    let leftPressed = false;
    let rightPressed = false;

    const keyDownHandler = (e) => {
      if (e.key === 'ArrowLeft') leftPressed = true;
      if (e.key === 'ArrowRight') rightPressed = true;
    };

    const keyUpHandler = (e) => {
      if (e.key === 'ArrowLeft') leftPressed = false;
      if (e.key === 'ArrowRight') rightPressed = false;
    };

    document.addEventListener('keydown', keyDownHandler);
    document.addEventListener('keyup', keyUpHandler);

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      // Draw platforms
      ctx.fillStyle = theme.buttonColor;
      platforms.forEach(platform => {
        ctx.fillRect(platform.x, platform.y - cameraY, platform.width, platform.height);
      });

      // Draw player
      ctx.fillStyle = theme.buttonColor;
      ctx.fillRect(player.x, player.y - cameraY, player.width, player.height);

      // Move player
      if (leftPressed) player.velocityX = -3;
      else if (rightPressed) player.velocityX = 3;
      else player.velocityX = 0;

      player.x += player.velocityX;
      player.velocityY += gravity;
      player.y += player.velocityY;

      // Wrap around
      if (player.x < 0) player.x = canvas.width;
      if (player.x > canvas.width) player.x = 0;

      // Platform collision
      if (player.velocityY > 0) {
        platforms.forEach(platform => {
          if (player.x + player.width > platform.x && player.x < platform.x + platform.width &&
              player.y + player.height > platform.y && player.y + player.height < platform.y + platform.height + 10) {
            player.velocityY = jumpPower;
            setScore(s => Math.max(s, Math.floor(cameraY / 10)));
          }
        });
      }

      // Camera follow
      if (player.y < cameraY + 200) {
        cameraY = player.y - 200;
      }

      // Add new platforms
      if (platforms[platforms.length - 1].y < cameraY + 500) {
        platforms.push({ x: Math.random() * 340, y: platforms[platforms.length - 1].y - 50, width: 60, height: 10 });
      }

      // Remove old platforms
      platforms = platforms.filter(p => p.y < cameraY + canvas.height + 100);

      // Game over
      if (player.y - cameraY > canvas.height) {
        setGameOver(true);
        return;
      }

      if (!gameOver) {
        requestAnimationFrame(draw);
      }
    }

    draw();

    return () => {
      document.removeEventListener('keydown', keyDownHandler);
      document.removeEventListener('keyup', keyUpHandler);
    };
  }, [gameStarted, gameOver, theme]);

  const resetGame = () => {
    setScore(0);
    setGameOver(false);
    setGameStarted(true);
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Doodle Jump</h2>
      <div className="text-xl mb-4">Score: {score}</div>
      <canvas ref={canvasRef} width="400" height="500" className="border rounded" style={{ backgroundColor: theme.bgColor, borderColor: theme.textColor + '20' }} />
      {!gameStarted && (
        <div className="mt-4">
          <Button onClick={() => setGameStarted(true)} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Start Game</Button>
        </div>
      )}
      {gameOver && (
        <div className="mt-4">
          <p className="text-xl mb-4">Game Over! Score: {score}</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Arrow keys to move</p>
    </div>
  );
}

function TetrisGame({ theme }) {
  const [board, setBoard] = useState(Array(20).fill(null).map(() => Array(10).fill(0)));
  const [currentPiece, setCurrentPiece] = useState(null);
  const [position, setPosition] = useState({ x: 4, y: 0 });
  const [score, setScore] = useState(0);
  const [gameOver, setGameOver] = useState(false);
  const [gameStarted, setGameStarted] = useState(false);

  const pieces = [
    [[1,1,1,1]], // I
    [[1,1],[1,1]], // O
    [[0,1,0],[1,1,1]], // T
    [[1,0,0],[1,1,1]], // L
    [[0,0,1],[1,1,1]], // J
    [[0,1,1],[1,1,0]], // S
    [[1,1,0],[0,1,1]]  // Z
  ];

  useEffect(() => {
    if (!gameStarted || gameOver) return;
    if (!currentPiece) {
      const newPiece = pieces[Math.floor(Math.random() * pieces.length)];
      setCurrentPiece(newPiece);
      setPosition({ x: 4, y: 0 });
    }
  }, [currentPiece, gameStarted, gameOver]);

  useEffect(() => {
    if (!gameStarted || gameOver || !currentPiece) return;

    const interval = setInterval(() => {
      moveDown();
    }, 500);

    return () => clearInterval(interval);
  }, [position, currentPiece, board, gameStarted, gameOver]);

  useEffect(() => {
    const handleKeyPress = (e) => {
      if (!gameStarted || gameOver || !currentPiece) return;
      
      if (e.key === 'ArrowLeft') moveLeft();
      if (e.key === 'ArrowRight') moveRight();
      if (e.key === 'ArrowDown') moveDown();
      if (e.key === 'ArrowUp') rotate();
    };

    window.addEventListener('keydown', handleKeyPress);
    return () => window.removeEventListener('keydown', handleKeyPress);
  }, [position, currentPiece, board, gameStarted, gameOver]);

  const canMove = (piece, pos) => {
    for (let y = 0; y < piece.length; y++) {
      for (let x = 0; x < piece[y].length; x++) {
        if (piece[y][x]) {
          const newX = pos.x + x;
          const newY = pos.y + y;
          if (newX < 0 || newX >= 10 || newY >= 20) return false;
          if (newY >= 0 && board[newY][newX]) return false;
        }
      }
    }
    return true;
  };

  const moveDown = () => {
    const newPos = { x: position.x, y: position.y + 1 };
    if (canMove(currentPiece, newPos)) {
      setPosition(newPos);
    } else {
      lockPiece();
    }
  };

  const moveLeft = () => {
    const newPos = { x: position.x - 1, y: position.y };
    if (canMove(currentPiece, newPos)) {
      setPosition(newPos);
    }
  };

  const moveRight = () => {
    const newPos = { x: position.x + 1, y: position.y };
    if (canMove(currentPiece, newPos)) {
      setPosition(newPos);
    }
  };

  const rotate = () => {
    const rotated = currentPiece[0].map((_, i) => currentPiece.map(row => row[i]).reverse());
    if (canMove(rotated, position)) {
      setCurrentPiece(rotated);
    }
  };

  const lockPiece = () => {
    const newBoard = board.map(row => [...row]);
    for (let y = 0; y < currentPiece.length; y++) {
      for (let x = 0; x < currentPiece[y].length; x++) {
        if (currentPiece[y][x]) {
          const boardY = position.y + y;
          const boardX = position.x + x;
          if (boardY < 0) {
            setGameOver(true);
            return;
          }
          newBoard[boardY][boardX] = 1;
        }
      }
    }

    // Clear lines
    let linesCleared = 0;
    for (let y = 19; y >= 0; y--) {
      if (newBoard[y].every(cell => cell === 1)) {
        newBoard.splice(y, 1);
        newBoard.unshift(Array(10).fill(0));
        linesCleared++;
        y++;
      }
    }

    setScore(s => s + linesCleared * 100);
    setBoard(newBoard);
    setCurrentPiece(null);
  };

  const renderBoard = () => {
    const displayBoard = board.map(row => [...row]);
    if (currentPiece) {
      for (let y = 0; y < currentPiece.length; y++) {
        for (let x = 0; x < currentPiece[y].length; x++) {
          if (currentPiece[y][x] && position.y + y >= 0) {
            displayBoard[position.y + y][position.x + x] = 2;
          }
        }
      }
    }
    return displayBoard;
  };

  const resetGame = () => {
    setBoard(Array(20).fill(null).map(() => Array(10).fill(0)));
    setCurrentPiece(null);
    setPosition({ x: 4, y: 0 });
    setScore(0);
    setGameOver(false);
    setGameStarted(true);
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Tetris</h2>
      <div className="text-xl mb-4">Score: {score}</div>
      <div className="inline-block p-4" style={{ backgroundColor: theme.tileColor, borderRadius: '0.5rem' }}>
        <div className="grid gap-[1px]" style={{ gridTemplateColumns: 'repeat(10, 20px)' }}>
          {renderBoard().map((row, y) => row.map((cell, x) => (
            <div
              key={`${y}-${x}`}
              className="w-5 h-5"
              style={{
                backgroundColor: cell === 2 ? theme.buttonColor : cell === 1 ? theme.textColor : theme.bgColor,
                border: `1px solid ${theme.textColor}20`
              }}
            />
          )))}
        </div>
      </div>
      {!gameStarted && (
        <div className="mt-4">
          <Button onClick={() => setGameStarted(true)} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Start Game</Button>
        </div>
      )}
      {gameOver && (
        <div className="mt-4">
          <p className="text-xl mb-4">Game Over! Score: {score}</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Arrow keys: ← → move, ↓ drop, ↑ rotate</p>
    </div>
  );
}

function SimonGame({ theme }) {
  const [sequence, setSequence] = useState([]);
  const [playerSequence, setPlayerSequence] = useState([]);
  const [isPlaying, setIsPlaying] = useState(false);
  const [activeButton, setActiveButton] = useState(null);
  const [score, setScore] = useState(0);
  const [gameOver, setGameOver] = useState(false);
  const colors = ['red', 'blue', 'green', 'yellow'];

  const startGame = () => {
    setSequence([]);
    setPlayerSequence([]);
    setScore(0);
    setGameOver(false);
    addToSequence([]);
  };

  const addToSequence = (currentSeq) => {
    const newColor = colors[Math.floor(Math.random() * 4)];
    const newSequence = [...currentSeq, newColor];
    setSequence(newSequence);
    playSequence(newSequence);
  };

  const playSequence = async (seq) => {
    setIsPlaying(true);
    for (let color of seq) {
      await new Promise(resolve => setTimeout(resolve, 200));
      setActiveButton(color);
      await new Promise(resolve => setTimeout(resolve, 500));
      setActiveButton(null);
    }
    setIsPlaying(false);
  };

  const handleColorClick = (color) => {
    if (isPlaying || gameOver) return;
    
    const newPlayerSequence = [...playerSequence, color];
    setPlayerSequence(newPlayerSequence);
    setActiveButton(color);
    setTimeout(() => setActiveButton(null), 300);

    if (newPlayerSequence[newPlayerSequence.length - 1] !== sequence[newPlayerSequence.length - 1]) {
      setGameOver(true);
      return;
    }

    if (newPlayerSequence.length === sequence.length) {
      setScore(score + 1);
      setPlayerSequence([]);
      setTimeout(() => addToSequence(sequence), 1000);
    }
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Simon Says</h2>
      <div className="text-xl mb-6">Score: {score}</div>
      <div className="grid grid-cols-2 gap-4 max-w-md mx-auto mb-6">
        {colors.map(color => (
          <button
            key={color}
            onClick={() => handleColorClick(color)}
            disabled={isPlaying || gameOver}
            className="aspect-square rounded-lg transition-all"
            style={{
              backgroundColor: color,
              opacity: activeButton === color ? 1 : 0.6,
              transform: activeButton === color ? 'scale(0.95)' : 'scale(1)',
              cursor: isPlaying || gameOver ? 'not-allowed' : 'pointer'
            }}
          />
        ))}
      </div>
      {gameOver && (
        <div className="mb-4">
          <p className="text-xl mb-4">Game Over! Final Score: {score}</p>
          <Button onClick={startGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      {!gameOver && sequence.length === 0 && (
        <Button onClick={startGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Start Game</Button>
      )}
    </div>
  );
}

function WhackAMole({ theme }) {
  const [moles, setMoles] = useState(Array(9).fill(false));
  const [score, setScore] = useState(0);
  const [timeLeft, setTimeLeft] = useState(30);
  const [gameActive, setGameActive] = useState(false);

  useEffect(() => {
    if (!gameActive) return;

    const timer = setInterval(() => {
      setTimeLeft(prev => {
        if (prev <= 1) {
          setGameActive(false);
          return 0;
        }
        return prev - 1;
      });
    }, 1000);

    return () => clearInterval(timer);
  }, [gameActive]);

  useEffect(() => {
    if (!gameActive) return;

    const moleTimer = setInterval(() => {
      const newMoles = Array(9).fill(false);
      const randomIndex = Math.floor(Math.random() * 9);
      newMoles[randomIndex] = true;
      setMoles(newMoles);
    }, 800);

    return () => clearInterval(moleTimer);
  }, [gameActive]);

  const startGame = () => {
    setScore(0);
    setTimeLeft(30);
    setGameActive(true);
    setMoles(Array(9).fill(false));
  };

  const whackMole = (index) => {
    if (!gameActive || !moles[index]) return;
    setScore(score + 1);
    setMoles(prev => prev.map((m, i) => i === index ? false : m));
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Whack-a-Mole</h2>
      <div className="flex justify-between items-center mb-6 max-w-md mx-auto">
        <div className="text-xl">Score: {score}</div>
        <div className="text-xl">Time: {timeLeft}s</div>
      </div>
      <div className="grid grid-cols-3 gap-4 max-w-md mx-auto mb-6">
        {moles.map((isMoleUp, index) => (
          <button
            key={index}
            onClick={() => whackMole(index)}
            className="aspect-square rounded-lg flex items-center justify-center text-4xl transition-all"
            style={{
              backgroundColor: theme.tileColor,
              border: `2px solid ${theme.textColor}20`,
              cursor: gameActive ? 'pointer' : 'not-allowed',
              transform: isMoleUp ? 'scale(1.1)' : 'scale(1)'
            }}
          >
            {isMoleUp ? '🦫' : '🕳️'}
          </button>
        ))}
      </div>
      {!gameActive && timeLeft === 30 && (
        <Button onClick={startGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Start Game</Button>
      )}
      {!gameActive && timeLeft === 0 && (
        <div>
          <p className="text-xl mb-4">Game Over! Final Score: {score}</p>
          <Button onClick={startGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
    </div>
  );
}

function CrossyRoad({ theme }) {
  const [playerPos, setPlayerPos] = useState({ x: 5, y: 9 });
  const [cars, setCars] = useState([]);
  const [score, setScore] = useState(0);
  const [gameOver, setGameOver] = useState(false);
  const gridWidth = 11;
  const gridHeight = 10;

  useEffect(() => {
    const initialCars = [];
    for (let row = 1; row < 9; row++) {
      if (Math.random() > 0.5) {
        initialCars.push({ x: Math.floor(Math.random() * gridWidth), y: row, dir: Math.random() > 0.5 ? 1 : -1 });
      }
    }
    setCars(initialCars);
  }, []);

  useEffect(() => {
    if (gameOver) return;

    const moveCars = setInterval(() => {
      setCars(prev => prev.map(car => ({
        ...car,
        x: (car.x + car.dir + gridWidth) % gridWidth
      })));
    }, 500);

    return () => clearInterval(moveCars);
  }, [gameOver]);

  useEffect(() => {
    if (gameOver) return;

    const collision = cars.some(car => car.x === playerPos.x && car.y === playerPos.y);
    if (collision) {
      setGameOver(true);
    }
  }, [playerPos, cars, gameOver]);

  useEffect(() => {
    const handleKeyPress = (e) => {
      if (gameOver) return;
      
      setPlayerPos(prev => {
        let newPos = { ...prev };
        if (e.key === 'ArrowUp' && prev.y > 0) {
          newPos.y = prev.y - 1;
          setScore(s => s + 1);
        }
        if (e.key === 'ArrowDown' && prev.y < gridHeight - 1) newPos.y = prev.y + 1;
        if (e.key === 'ArrowLeft' && prev.x > 0) newPos.x = prev.x - 1;
        if (e.key === 'ArrowRight' && prev.x < gridWidth - 1) newPos.x = prev.x + 1;
        return newPos;
      });
    };

    window.addEventListener('keydown', handleKeyPress);
    return () => window.removeEventListener('keydown', handleKeyPress);
  }, [gameOver]);

  const resetGame = () => {
    setPlayerPos({ x: 5, y: 9 });
    setScore(0);
    setGameOver(false);
    const initialCars = [];
    for (let row = 1; row < 9; row++) {
      if (Math.random() > 0.5) {
        initialCars.push({ x: Math.floor(Math.random() * gridWidth), y: row, dir: Math.random() > 0.5 ? 1 : -1 });
      }
    }
    setCars(initialCars);
  };

  return (
    <div className="max-w-2xl mx-auto text-center">
      <h2 className="font-heading text-2xl mb-4">Crossy Road</h2>
      <div className="text-xl mb-4">Score: {score}</div>
      <div className="inline-block p-4" style={{ backgroundColor: theme.tileColor, borderRadius: '0.5rem' }}>
        <div style={{ display: 'grid', gridTemplateColumns: `repeat(${gridWidth}, 30px)`, gap: '2px' }}>
          {Array.from({ length: gridHeight * gridWidth }).map((_, i) => {
            const x = i % gridWidth;
            const y = Math.floor(i / gridWidth);
            const isPlayer = playerPos.x === x && playerPos.y === y;
            const hasCar = cars.some(car => car.x === x && car.y === y);
            const isRoad = y > 0 && y < 9;
            
            return (
              <div
                key={i}
                className="w-[30px] h-[30px] flex items-center justify-center text-lg"
                style={{
                  backgroundColor: isRoad ? '#555' : '#90EE90',
                  border: `1px solid ${theme.textColor}20`
                }}
              >
                {isPlayer ? '🐔' : hasCar ? '🚗' : ''}
              </div>
            );
          })}
        </div>
      </div>
      {gameOver && (
        <div className="mt-4">
          <p className="text-xl mb-4">Game Over! Final Score: {score}</p>
          <Button onClick={resetGame} style={{ backgroundColor: theme.buttonColor, color: '#ffffff' }}>Play Again</Button>
        </div>
      )}
      <p className="text-sm mt-4" style={{ opacity: 0.7 }}>Use arrow keys to move</p>
    </div>
  );
}
