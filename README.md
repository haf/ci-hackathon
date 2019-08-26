# The KTH Continuous Integration Hackathon

> We build beautiful visualizations or sonifications of continuous integration (of compilation, test, analysis, packaging, deployment, etc).

## The Concept

For months, we prepare our prototypes about CI data and activity. On October 14 2019, we meet in the nuclear reactor R1 at KTH for a unique moment of art and software technology.

## Participants

To participate to the hackathon, simply make a pull-request on this repo.

Participants:
s
- Thomas Durieux: 
    * [Continuous Integration Rain](https://travis.durieux.me/rain.html) [repo](https://travis-ci.com/tdurieux/travis-listener/)
    * [Travis Drum](https://kth.github.io/ci-hackathon/solutions/tdurieux_drum_tdurieux) based on https://codepen.io/teropa/pen/PKoYXM
    * [Travis Canvas](https://travis.durieux.me/canvas.html) 
    * [Travis Tree](https://travis.durieux.me/tree/) based on https://github.com/guo2/tree_js
- Long Zhang: [The King of CI Fighters](https://youtu.be/94_OSJQFY9Q) (details in folder [king_of_ci_fighters](king_of_ci_fighters))
- Simone Stefani: sonification with chords (details in folder [stefani](stefani))
- Javier Cabrera and Benoit Baudry: 
    * [The pulse of Travis](https://kth.github.io/ci-hackathon/solutions/Jacarte_bbaudry_pulse_of_travis)
    * [The voice of Travis](https://kth.github.io/ci-hackathon/solutions/Jacarte_bbaudry_voice_of_travis) 
- Oscar Luis Vera Pérez: [The Travis CI Drum Machine](https://kth.github.io/ci-hackathon/solutions/oscarlvp_drum-machine.html)
- Add your name / your team with a pull request :-)

## Program of October 14 2019

- 18:00 Welcome talk by hackathon curator Benoit Baudry
- 18:20 Reading of Code (performer TBA)
- 18:30 Demo and explanation of the Travis API / Websocket (Thomas Durieux)
- 18:40 Demo and Explanation of the organ interface (Simone Stefani)
- 18:50 Demo and Explanation of the light interface (TBA)
- 19h00 - 22:00: Pizza, beer and coding
- 22h00 CI Rain: Thomas Durieux
- 22h15 TBA
- 22h30 TBA
- 22h45 TBA

## Technology

### Travis API

We use Travis CI as main source of data. Travis CI provides different API end-points to listen to their builds. Reference documentation: <https://docs.travis-ci.com/user/developer/>

### WebSocket

A websocket with Travis builds is available at <ws://travis.durieux.me>.

PYTHON: `pip3 install websocket_client`

```python
import websocket
def on_message(ws, message):
    print(message)

websocket.enableTrace(True)
ws = websocket.WebSocketApp("wss://travis.durieux.me/",on_message = on_message)
ws.run_forever()
```

JAVASCRIPT

```js
ws = new WebSocket('wss://travis.durieux.me’);
ws.onmessage = console.log
```

More information is available [here](https://github.com/KTH/ci-hackathon/blob/master/ci-ws-documentation.md).

### Travis Listener (NodeJS)

[Travis Listener](https://github.com/tdurieux/travis-listener) provides a websocket server for easier use ([documentation](https://durieux.me/projects/travis_listener.html))

### Visualization

- [D3.js](https://d3js.org/)
- [P5.js](https://p5js.org/)
- [Vega Lite](https://vega.github.io/vega-lite/)

### Sonification

For sonification, one can use the library [tone.js](https://tonejs.github.io/)

## Frequently Asked Questions

- **I'm looking for partners, I'd like to create or join a team?**

  Simply create an issue on this repository and tell what you are looking for.

- **How do I add my information as a participant?**

   Yes, we also use Travis to construct this site. Basically, we walk trough our repo to catch every team and every solution by team, and then, we construct this site with the collected information. Just follow these instructions to register a team:
   1. Fork the project
   2. Create a folder inside "participants" with your team member github ids separated by underscore as a name, for example: ```id1_id2_...idn```.
   4. **Optional** Create a ```Readme.md``` file with the content that you want to show in your team page (By deafult we list your solutions and put them in an autogenerated file)
   3. Put any solution of yours in the previous folder
   5. **Options** We create a page for each solution, just create a ```Readme.md``` inside your solution folder and we will add it as a page in the site.
   6. Create a pull request to master
   7. And thats all !!.
   