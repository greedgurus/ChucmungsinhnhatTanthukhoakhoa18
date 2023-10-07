# VuThuyCute
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* Kaushan+Script, oregano, sail */
        @import url("https://fonts.googleapis.com/css?family=Kaushan+Script");

        html,
        body,
        .container {
            height: 100%;
            font-family: "Kaushan Script", "Sail", cursive;
        }

        body {
            background: #e74;
            overflow: hidden;
            background-image: linear-gradient(to bottom, #190e14, #0d0d4b 30%, #c76075 80%, #e9b64b 95%);
            background-image: radial-gradient(circle at center bottom, #e9b64b, #c76075 15%, #0d0d4b 75%, #190e14 90%);
            z-index: 99;
        }

        div#beach,
        canvas#canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 99;
        }

        div#beach {
            background-image: url(https://dl.dropbox.com/s/oe0oce2udq44bj5/beachsil2.png);
            /* background-size: cover; */
            background-position: bottom right;
            background-size: 1700px;
            background-repeat: no-repeat;
        }

        div#video {
            position: absolute;
            right: 243px;
            bottom: 200px;
        }

        div#video iframe {
            width: 255px;
            height: 155px;
        }

        #people {
            position: absolute;
            bottom: 65px;
            left: 40px;
            width: 140px;
        }

        #car {
            position: absolute;
            bottom: 46px;
            left: 180px;
            width: 230px;
        }

        div#sea {
            background-color: blue;
            height: 85px;
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background-image: radial-gradient(circle at center top, #23485a, #0d0246);
        }

        .merrywrap {
            position: absolute;
            right: 0px;
            left: 0px;
            bottom: 0px;
            top: 0px;
            background-color: antiquewhite;
            transition: background-color 0.5s ease;
            z-index: 1000;
            height: 102vh;
        }

        .giftbox {
            position: absolute;
            width: 300px;
            height: 200px;
            left: 50%;
            margin-left: -150px;
            top: 40%;
            z-index: 10;
        }

        .giftbox>div {
            background: #d44;
            position: absolute;
        }

        .giftbox>div:after,
        .giftbox>div:before {
            position: absolute;
            content: "";
            top: 0;
        }

        .giftbox:after {
            position: absolute;
            color: #fff;
            width: 100%;
            content: "Click Me!";
            left: 0;
            bottom: 0;
            font-size: 50px;
            text-align: center;
            transform: rotate(-20deg);
            transform-origin: 0 0;

        }

        .giftbox .cover {
            width: 100%;
            top: 0;
            left: 0;
            height: 25%;
            z-index: 2;
        }

        .giftbox .cover:before {
            position: absolute;
            height: 100%;
            left: 50%;
            width: 50px;
            transform: translateX(-50%);
            background: #fdc56d;
        }

        .giftbox .cover>div {
            position: absolute;
            width: 50px;
            height: 50px;
            left: 50%;
            top: -50px;
            transform: translateX(-50%);
        }

        .giftbox .cover>div:before,
        .giftbox .cover>div:after {
            position: absolute;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            content: "";
            box-shadow: inset 0 0 0 15px #fdc56d;
            border-radius: 30px;
            transform-origin: 50% 100%;
        }

        .giftbox .cover>div:before {
            transform: translateX(-45%) skewY(40deg);
        }

        .giftbox .cover>div:after {
            transform: translateX(45%) skewY(-40deg);
        }

        .giftbox .box {
            right: 5%;
            left: 5%;
            height: 80%;
            bottom: 0;
        }

        .giftbox .box:before {
            width: 50px;
            height: 100%;
            left: 50%;
            transform: translateX(-50%);
            background: #fdc56d;
        }

        .giftbox .box:after {
            width: 100%;
            height: 30px;
            background: rgba(0, 0, 0, 0.2);
        }

        .icons {
            position: absolute;
            left: 10px;
            /*top:50%;
  width: 100%;*/
            height: auto;
            transform: translateY(10px) rotate(-20deg);
        }

        .icons .row {
            width: 100%;
            text-align: center;
        }

        .icons .row span {
            color: #e5e5e5;
            text-shadow: 4px 4px 0 rgba(96, 125, 139, 0.4);
            font-size: 50px;
            display: inline-block;
            opacity: 0;
            transition: transform 0.5s ease-in, opacity 0.7s;
        }

        .step-1 .giftbox {
            animation: wobble 0.5s linear infinite forwards;
        }

        .step-1 .cover {
            animation: wobble 0.5s linear infinite 0.1s forwards;
        }

        .step-1 .icons .row span {
            opacity: 1;
        }

        .step-2 .giftbox:after {
            opacity: 0;
        }

        .step-3 .giftbox,
        .step-4 .giftbox {
            opacity: 0;
            z-index: 1;
        }

        .step-3 .giftbox:after,
        .step-4 .giftbox:after {
            opacity: 0;
        }

        .step-2 .giftbox .cover {
            animation: flyUp 0.4s ease-in forwards;
        }

        .step-2 .giftbox .box {
            animation: flyDown 0.2s ease-in 0.05s forwards;
        }

        @keyframes wobble {
            25% {
                transform: rotate(4deg);
            }

            75% {
                transform: rotate(-2deg);
            }
        }

        @keyframes flyUp {
            75% {
                opacity: 1;
            }

            100% {
                transform: translateY(-1000px) rotate(20deg);
                opacity: 0;
            }
        }

        @keyframes flyDown {
            75% {
                opacity: 1;
            }

            100% {
                transform: translateY(100%);
                opacity: 0;
            }
        }

        .step-1 .icons .row span {
            opacity: 0;
        }

        .step-1 .icons .row span:first-child {
            transform: translateY(700%) translateX(600%);
        }

        .step-1 .icons .row span:nth-child(2) {
            transform: translateY(700%) translateX(500%);
        }

        .step-1 .icons .row span:nth-child(3) {
            transform: translateY(700%) translateX(400%);
        }

        .step-1 .icons .row span:nth-child(4) {
            transform: translateY(700%) translateX(300%);
        }

        .step-1 .icons .row span:nth-child(5) {
            transform: translateY(700%) translateX(200%);
        }

        .step-1 .icons .row span:nth-child(6) {
            transform: translateY(700%) translateX(100%);
        }

        .step-1 .icons .row span:nth-child(7) {
            transform: translateY(700%) translateX(0);
        }

        .step-1 .icons .row span:nth-child(8) {
            transform: translateY(700%) translateX(-100%);
        }

        .step-1 .icons .row span:nth-child(9) {
            transform: translateY(700%) translateX(-200%);
        }

        .step-1 .icons .row span:nth-child(10) {
            transform: translateY(700%) translateX(-300%);
        }

        .step-1 .icons .row span:nth-child(11) {
            transform: translateY(700%) translateX(-400%);
        }

        .step-1 .icons .row span:nth-child(12) {
            transform: translateY(700%) translateX(-500%);
        }

        .step-1 .icons .row span:nth-child(13) {
            transform: translateY(700%) translateX(-600%);
        }

        .step-2 .icons .row span:nth-child(2) {
            -webkit-transition-delay: 0.1s;
            transition-delay: 0.1s;
        }

        .step-2 .icons .row span:nth-child(3) {
            -webkit-transition-delay: 0.15s;
            transition-delay: 0.15s;
        }

        .step-2 .icons .row span:nth-child(4) {
            -webkit-transition-delay: 0.2s;
            transition-delay: 0.2s;
        }

        .step-2 .icons .row span:nth-child(5) {
            -webkit-transition-delay: 0.25s;
            transition-delay: 0.25s;
        }

        .step-2 .icons .row span:nth-child(6) {
            -webkit-transition-delay: 0.3s;
            transition-delay: 0.3s;
        }

        .step-2 .icons .row span:nth-child(7) {
            -webkit-transition-delay: 0.35s;
            transition-delay: 0.35s;
        }

        .step-2 .icons .row span:nth-child(8) {
            -webkit-transition-delay: 0.4s;
            transition-delay: 0.4s;
        }

        .step-2 .icons .row span:nth-child(9) {
            -webkit-transition-delay: 0.45s;
            transition-delay: 0.45s;
        }

        .step-2 .icons .row span:nth-child(10) {
            -webkit-transition-delay: 0.5s;
            transition-delay: 0.5s;
        }

        .step-2 .icons .row span:nth-child(11) {
            -webkit-transition-delay: 0.55s;
            transition-delay: 0.55s;
        }

        .step-2 .icons .row span:nth-child(12) {
            -webkit-transition-delay: 0.6s;
            transition-delay: 0.6s;
        }

        .step-2 .icons .row span:nth-child(13) {
            -webkit-transition-delay: 0.65s;
            transition-delay: 0.65s;
        }

        .step-2 .icons span,
        .step-3 .icons span,
        .step-4 .icons span {
            opacity: 1;
            transition-timing-function: cubic-bezier(0, 0, 0.2, 0.91);
        }

        .step-4 .icons .row span,
        .step-3 .icons .row span {
            /*animation: wobble 0.6s linear infinite forwards;*/
            color: #c6e2ff;
            animation: neon 0.08s ease-in-out infinite alternate;
        }

        .step-4 .icons .row span:nth-child(even),
        .step-3 .icons .row span:nth-child(even) {
            animation-duration: 0.7s;
        }

        @keyframes neon {
            from {
                text-shadow: 0 0 6px rgba(202, 228, 225, 0.92), 0 0 30px rgba(202, 228, 225, 0.34), 0 0 12px rgba(30, 132, 242, 0.52), 0 0 21px rgba(30, 132, 242, 0.92), 0 0 34px rgba(30, 132, 242, 0.78), 0 0 54px rgba(30, 132, 242, 0.92);
            }

            to {
                text-shadow: 0 0 6px rgba(202, 228, 225, 0.98), 0 0 30px rgba(202, 228, 225, 0.42), 0 0 12px rgba(30, 132, 242, 0.58), 0 0 22px rgba(30, 132, 242, 0.84), 0 0 38px rgba(30, 132, 242, 0.88), 0 0 60px #1e84f2;
            }
        }

        .moon {
            position: absolute;
            top: 10%;
            right: 200px;
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: #ddd;
            box-shadow: inset 20px -10px 0 0 #b9b9b9;
        }

        .moon .crater1 {
            position: absolute;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background: #bbb;
            box-shadow: inset -3px 1.5px 0 0 #aaa;
            top: 20px;
            right: 20px;
        }

        .moon .crater2 {
            position: absolute;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: #bbb;
            box-shadow: inset -1px 0.5px 0 0 #aaa;
            top: 45px;
            right: 50px;
        }

        .moon .crater3 {
            position: absolute;
            width: 15px;
            height: 15px;
            border-radius: 50%;
            background: #bbb;
            box-shadow: inset -1.5px 0.75px 0 0 #aaa;
            top: 60px;
            right: 25px;
        }

        @media (min-width: 1000px) {
            .icons {
                left: 30px;
            }

            .icons .row span {
                font-size: 56px;
            }

            #people {
                left: 80px;
                bottom: 70px;
                width: 160px;
            }

            div#beach {
                background-size: 2000px;
            }

            div#video {
                right: 290px;
                bottom: 235px;
            }

            div#video iframe {
                width: 295px;
                height: 185px;
            }

            .moon {
                right: 230px;
            }
        }

        canvas#c {
            position: absolute;
            top: 0;
            left: 0;
        }
    </style>

    <style>
      

        #balloon-container {
            height: 100vh;
            padding: 1em;
            box-sizing: border-box;
            display: flex;
            flex-wrap: wrap;
            overflow: hidden;
            transition: opacity 500ms;
        }

        .balloon {
            height: 125px;
            width: 105px;
            border-radius: 75% 75% 70% 70%;
            position: relative;
        }

        .balloon:before {
            content: "";
            height: 75px;
            width: 1px;
            padding: 1px;
            background-color: #FDFD96;
            display: block;
            position: absolute;
            top: 125px;
            left: 0;
            right: 0;
            margin: auto;
        }

        .balloon:after {
            content: "▲";
            text-align: center;
            display: block;
            position: absolute;
            color: inherit;
            top: 120px;
            left: 0;
            right: 0;
            margin: auto;
        }

        @keyframes float {
            from {
                transform: translateY(100vh);
                opacity: 1;
            }

            to {
                transform: translateY(-300vh);
                opacity: 0;
            }
        }
    </style>
</head>

<body>
  

    <canvas id="canvas"></canvas>
    <div id="merrywrap" class="merrywrap">
        <div class="giftbox">
            <div class="cover">
                <div></div>
            </div>
            <div class="box"></div>
        </div>

    </div>
    <canvas id="c"></canvas>
    <div id="balloon-container">
    </div>
  

    <script>
        var w = c.width = window.innerWidth,
            h = c.height = window.innerHeight,
            ctx = c.getContext('2d'),

            hw = w / 2, // half-width
            hh = h / 2,

            opts = {
                strings: ['HAPPY', 'BIRTHDAY!', 'VŨ THỊ THÚY'],
                charSize: 120,
                charSpacing: 120,
                lineHeight: 120,

                cx: w / 2,
                cy: h / 2,

                fireworkPrevPoints: 10,
                fireworkBaseLineWidth: 5,
                fireworkAddedLineWidth: 8,
                fireworkSpawnTime: 200,
                fireworkBaseReachTime: 30,
                fireworkAddedReachTime: 30,
                fireworkCircleBaseSize: 20,
                fireworkCircleAddedSize: 10,
                fireworkCircleBaseTime: 30,
                fireworkCircleAddedTime: 30,
                fireworkCircleFadeBaseTime: 10,
                fireworkCircleFadeAddedTime: 5,
                fireworkBaseShards: 5,
                fireworkAddedShards: 5,
                fireworkShardPrevPoints: 3,
                fireworkShardBaseVel: 4,
                fireworkShardAddedVel: 2,
                fireworkShardBaseSize: 3,
                fireworkShardAddedSize: 3,
                gravity: .1,
                upFlow: -.1,
                letterContemplatingWaitTime: 360,
                balloonSpawnTime: 20,
                balloonBaseInflateTime: 10,
                balloonAddedInflateTime: 10,
                balloonBaseSize: 20,
                balloonAddedSize: 20,
                balloonBaseVel: .4,
                balloonAddedVel: .4,
                balloonBaseRadian: -(Math.PI / 2 - .5),
                balloonAddedRadian: -1,
            },
            calc = {
                totalWidth: opts.charSpacing * Math.max(opts.strings[0].length, opts.strings[1].length)
            },

            Tau = Math.PI * 2,
            TauQuarter = Tau / 4,

            letters = [];

        ctx.font = opts.charSize + 'px Verdana';

        function Letter(char, x, y) {
            this.char = char;
            this.x = x;
            this.y = y;

            this.dx = -ctx.measureText(char).width / 2;
            this.dy = +opts.charSize / 2;

            this.fireworkDy = this.y - hh;

            var hue = x / calc.totalWidth * 360;

            this.color = 'hsl(hue,80%,50%)'.replace('hue', hue);
            this.lightAlphaColor = 'hsla(hue,80%,light%,alp)'.replace('hue', hue);
            this.lightColor = 'hsl(hue,80%,light%)'.replace('hue', hue);
            this.alphaColor = 'hsla(hue,80%,50%,alp)'.replace('hue', hue);

            this.reset();
        }
        Letter.prototype.reset = function () {

            this.phase = 'firework';
            this.tick = 0;
            this.spawned = false;
            this.spawningTime = opts.fireworkSpawnTime * Math.random() | 0;
            this.reachTime = opts.fireworkBaseReachTime + opts.fireworkAddedReachTime * Math.random() | 0;
            this.lineWidth = opts.fireworkBaseLineWidth + opts.fireworkAddedLineWidth * Math.random();
            this.prevPoints = [[0, hh, 0]];
        }
        Letter.prototype.step = function () {

            if (this.phase === 'firework') {

                if (!this.spawned) {

                    ++this.tick;
                    if (this.tick >= this.spawningTime) {

                        this.tick = 0;
                        this.spawned = true;
                    }

                } else {

                    ++this.tick;

                    var linearProportion = this.tick / this.reachTime,
                        armonicProportion = Math.sin(linearProportion * TauQuarter),

                        x = linearProportion * this.x,
                        y = hh + armonicProportion * this.fireworkDy;

                    if (this.prevPoints.length > opts.fireworkPrevPoints)
                        this.prevPoints.shift();

                    this.prevPoints.push([x, y, linearProportion * this.lineWidth]);

                    var lineWidthProportion = 1 / (this.prevPoints.length - 1);

                    for (var i = 1; i < this.prevPoints.length; ++i) {

                        var point = this.prevPoints[i],
                            point2 = this.prevPoints[i - 1];

                        ctx.strokeStyle = this.alphaColor.replace('alp', i / this.prevPoints.length);
                        ctx.lineWidth = point[2] * lineWidthProportion * i;
                        ctx.beginPath();
                        ctx.moveTo(point[0], point[1]);
                        ctx.lineTo(point2[0], point2[1]);
                        ctx.stroke();

                    }

                    if (this.tick >= this.reachTime) {

                        this.phase = 'contemplate';

                        this.circleFinalSize = opts.fireworkCircleBaseSize + opts.fireworkCircleAddedSize * Math.random();
                        this.circleCompleteTime = opts.fireworkCircleBaseTime + opts.fireworkCircleAddedTime * Math.random() | 0;
                        this.circleCreating = true;
                        this.circleFading = false;

                        this.circleFadeTime = opts.fireworkCircleFadeBaseTime + opts.fireworkCircleFadeAddedTime * Math.random() | 0;
                        this.tick = 0;
                        this.tick2 = 0;

                        this.shards = [];

                        var shardCount = opts.fireworkBaseShards + opts.fireworkAddedShards * Math.random() | 0,
                            angle = Tau / shardCount,
                            cos = Math.cos(angle),
                            sin = Math.sin(angle),

                            x = 1,
                            y = 0;

                        for (var i = 0; i < shardCount; ++i) {
                            var x1 = x;
                            x = x * cos - y * sin;
                            y = y * cos + x1 * sin;

                            this.shards.push(new Shard(this.x, this.y, x, y, this.alphaColor));
                        }
                    }

                }
            } else if (this.phase === 'contemplate') {

                ++this.tick;

                if (this.circleCreating) {

                    ++this.tick2;
                    var proportion = this.tick2 / this.circleCompleteTime,
                        armonic = -Math.cos(proportion * Math.PI) / 2 + .5;

                    ctx.beginPath();
                    ctx.fillStyle = this.lightAlphaColor.replace('light', 50 + 50 * proportion).replace('alp', proportion);
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, armonic * this.circleFinalSize, 0, Tau);
                    ctx.fill();

                    if (this.tick2 > this.circleCompleteTime) {
                        this.tick2 = 0;
                        this.circleCreating = false;
                        this.circleFading = true;
                    }
                } else if (this.circleFading) {

                    ctx.fillStyle = this.lightColor.replace('light', 70);
                    ctx.fillText(this.char, this.x + this.dx, this.y + this.dy);

                    ++this.tick2;
                    var proportion = this.tick2 / this.circleFadeTime,
                        armonic = -Math.cos(proportion * Math.PI) / 2 + .5;

                    ctx.beginPath();
                    ctx.fillStyle = this.lightAlphaColor.replace('light', 100).replace('alp', 1 - armonic);
                    ctx.arc(this.x, this.y, this.circleFinalSize, 0, Tau);
                    ctx.fill();

                    if (this.tick2 >= this.circleFadeTime)
                        this.circleFading = false;

                } else {

                    ctx.fillStyle = this.lightColor.replace('light', 70);
                    ctx.fillText(this.char, this.x + this.dx, this.y + this.dy);
                }

                for (var i = 0; i < this.shards.length; ++i) {

                    this.shards[i].step();

                    if (!this.shards[i].alive) {
                        this.shards.splice(i, 1);
                        --i;
                    }
                }

                if (this.tick > opts.letterContemplatingWaitTime) {

                    this.phase = 'balloon';

                    this.tick = 0;
                    this.spawning = true;
                    this.spawnTime = opts.balloonSpawnTime * Math.random() | 0;
                    this.inflating = false;
                    this.inflateTime = opts.balloonBaseInflateTime + opts.balloonAddedInflateTime * Math.random() | 0;
                    this.size = opts.balloonBaseSize + opts.balloonAddedSize * Math.random() | 0;

                    var rad = opts.balloonBaseRadian + opts.balloonAddedRadian * Math.random(),
                        vel = opts.balloonBaseVel + opts.balloonAddedVel * Math.random();

                    this.vx = Math.cos(rad) * vel;
                    this.vy = Math.sin(rad) * vel;
                }
            } else if (this.phase === 'balloon') {

                ctx.strokeStyle = this.lightColor.replace('light', 80);

                if (this.spawning) {

                    ++this.tick;
                    ctx.fillStyle = this.lightColor.replace('light', 70);
                    ctx.fillText(this.char, this.x + this.dx, this.y + this.dy);

                    if (this.tick >= this.spawnTime) {
                        this.tick = 0;
                        this.spawning = false;
                        this.inflating = true;
                    }
                } else if (this.inflating) {

                    ++this.tick;

                    var proportion = this.tick / this.inflateTime,
                        x = this.cx = this.x,
                        y = this.cy = this.y - this.size * proportion;

                    ctx.fillStyle = this.alphaColor.replace('alp', proportion);
                    ctx.beginPath();
                    generateBalloonPath(x, y, this.size * proportion);
                    ctx.fill();

                    ctx.beginPath();
                    ctx.moveTo(x, y);
                    ctx.lineTo(x, this.y);
                    ctx.stroke();

                    ctx.fillStyle = this.lightColor.replace('light', 70);
                    ctx.fillText(this.char, this.x + this.dx, this.y + this.dy);

                    if (this.tick >= this.inflateTime) {
                        this.tick = 0;
                        this.inflating = false;
                    }

                } else {

                    this.cx += this.vx;
                    this.cy += this.vy += opts.upFlow;

                    ctx.fillStyle = this.color;
                    ctx.beginPath();
                    generateBalloonPath(this.cx, this.cy, this.size);
                    ctx.fill();

                    ctx.beginPath();
                    ctx.moveTo(this.cx, this.cy);
                    ctx.lineTo(this.cx, this.cy + this.size);
                    ctx.stroke();

                    ctx.fillStyle = this.lightColor.replace('light', 70);
                    ctx.fillText(this.char, this.cx + this.dx, this.cy + this.dy + this.size);

                    if (this.cy + this.size < -hh || this.cx < -hw || this.cy > hw)
                        this.phase = 'done';

                }
            }
        }
        function Shard(x, y, vx, vy, color) {

            var vel = opts.fireworkShardBaseVel + opts.fireworkShardAddedVel * Math.random();

            this.vx = vx * vel;
            this.vy = vy * vel;

            this.x = x;
            this.y = y;

            this.prevPoints = [[x, y]];
            this.color = color;

            this.alive = true;

            this.size = opts.fireworkShardBaseSize + opts.fireworkShardAddedSize * Math.random();
        }
        Shard.prototype.step = function () {

            this.x += this.vx;
            this.y += this.vy += opts.gravity;

            if (this.prevPoints.length > opts.fireworkShardPrevPoints)
                this.prevPoints.shift();

            this.prevPoints.push([this.x, this.y]);

            var lineWidthProportion = this.size / this.prevPoints.length;

            for (var k = 0; k < this.prevPoints.length - 1; ++k) {

                var point = this.prevPoints[k],
                    point2 = this.prevPoints[k + 1];

                ctx.strokeStyle = this.color.replace('alp', k / this.prevPoints.length);
                ctx.lineWidth = k * lineWidthProportion;
                ctx.beginPath();
                ctx.moveTo(point[0], point[1]);
                ctx.lineTo(point2[0], point2[1]);
                ctx.stroke();

            }

            if (this.prevPoints[0][1] > hh)
                this.alive = false;
        }
        function generateBalloonPath(x, y, size) {

            ctx.moveTo(x, y);
            ctx.bezierCurveTo(x - size / 2, y - size / 2,
                x - size / 4, y - size,
                x, y - size);
            ctx.bezierCurveTo(x + size / 4, y - size,
                x + size / 2, y - size / 2,
                x, y);
        }

        function anim() {

            window.requestAnimationFrame(anim);

            ctx.fillStyle = '#111';
            ctx.fillRect(0, 0, w, h);

            ctx.translate(hw, hh);

            var done = true;
            for (var l = 0; l < letters.length; ++l) {

                letters[l].step();
                if (letters[l].phase !== 'done')
                    done = false;
            }

            ctx.translate(-hw, -hh);

            if (done)
                for (var l = 0; l < letters.length; ++l)
                    letters[l].reset();
        }

        for (var i = 0; i < opts.strings.length; ++i) {
            for (var j = 0; j < opts.strings[i].length; ++j) {
                letters.push(new Letter(opts.strings[i][j],
                    j * opts.charSpacing + opts.charSpacing / 2 - opts.strings[i].length * opts.charSize / 2,
                    i * opts.lineHeight + opts.lineHeight / 2 - opts.strings.length * opts.lineHeight / 2));
            }
        }

        setTimeout(() => {
            anim();

            ctx.font = opts.charSize + 'px Verdana';
        }, 2000);

        // window.addEventListener('resize', function () {

        //     w = c.width = window.innerWidth;
        //     h = c.height = window.innerHeight;

        //     hw = w / 2;
        //     hh = h / 2;

        //     ctx.font = opts.charSize + 'px Verdana';
        // })
    </script>

    <script>
        window.requestAnimFrame = (function () {
            return window.requestAnimationFrame ||
                window.webkitRequestAnimationFrame ||
                window.mozRequestAnimationFrame ||
                function (callback) {
                    window.setTimeout(callback, 1000 / 60);
                };
        })();

        // now we will setup our basic variables for the demo
        var canvas = document.getElementById('canvas'),
            ctx = canvas.getContext('2d'),
            // full screen dimensions
            cw = window.innerWidth,
            ch = window.innerHeight,
            // firework collection
            fireworks = [],
            // particle collection
            particles = [],
            // starting hue
            hue = 120,
            // when launching fireworks with a click, too many get launched at once without a limiter, one launch per 5 loop ticks
            limiterTotal = 5,
            limiterTick = 0,
            // this will time the auto launches of fireworks, one launch per 80 loop ticks
            timerTotal = 80,
            timerTick = 0,
            mousedown = false,
            // mouse x coordinate,
            mx,
            // mouse y coordinate
            my;

        // set canvas dimensions
        canvas.width = cw;
        canvas.height = ch;

        // now we are going to setup our function placeholders for the entire demo

        // get a random number within a range
        function random(min, max) {
            return Math.random() * (max - min) + min;
        }

        // calculate the distance between two points
        function calculateDistance(p1x, p1y, p2x, p2y) {
            var xDistance = p1x - p2x,
                yDistance = p1y - p2y;
            return Math.sqrt(Math.pow(xDistance, 2) + Math.pow(yDistance, 2));
        }

        // create firework
        function Firework(sx, sy, tx, ty) {
            // actual coordinates
            this.x = sx;
            this.y = sy;
            // starting coordinates
            this.sx = sx;
            this.sy = sy;
            // target coordinates
            this.tx = tx;
            this.ty = ty;
            // distance from starting point to target
            this.distanceToTarget = calculateDistance(sx, sy, tx, ty);
            this.distanceTraveled = 0;
            // track the past coordinates of each firework to create a trail effect, increase the coordinate count to create more prominent trails
            this.coordinates = [];
            this.coordinateCount = 3;
            // populate initial coordinate collection with the current coordinates
            while (this.coordinateCount--) {
                this.coordinates.push([this.x, this.y]);
            }
            this.angle = Math.atan2(ty - sy, tx - sx);
            this.speed = 2;
            this.acceleration = 1.05;
            this.brightness = random(50, 70);
            // circle target indicator radius
            this.targetRadius = 1;
        }

        // update firework
        Firework.prototype.update = function (index) {
            // remove last item in coordinates array
            this.coordinates.pop();
            // add current coordinates to the start of the array
            this.coordinates.unshift([this.x, this.y]);

            // cycle the circle target indicator radius
            if (this.targetRadius < 8) {
                this.targetRadius += 0.3;
            } else {
                this.targetRadius = 1;
            }

            // speed up the firework
            this.speed *= this.acceleration;

            // get the current velocities based on angle and speed
            var vx = Math.cos(this.angle) * this.speed,
                vy = Math.sin(this.angle) * this.speed;
            // how far will the firework have traveled with velocities applied?
            this.distanceTraveled = calculateDistance(this.sx, this.sy, this.x + vx, this.y + vy);

            // if the distance traveled, including velocities, is greater than the initial distance to the target, then the target has been reached
            if (this.distanceTraveled >= this.distanceToTarget) {
                createParticles(this.tx, this.ty);
                // remove the firework, use the index passed into the update function to determine which to remove
                fireworks.splice(index, 1);
            } else {
                // target not reached, keep traveling
                this.x += vx;
                this.y += vy;
            }
        }

        // draw firework
        Firework.prototype.draw = function () {
            ctx.beginPath();
            // move to the last tracked coordinate in the set, then draw a line to the current x and y
            ctx.moveTo(this.coordinates[this.coordinates.length - 1][0], this.coordinates[this.coordinates.length - 1][1]);
            ctx.lineTo(this.x, this.y);
            ctx.strokeStyle = 'hsl(' + hue + ', 100%, ' + this.brightness + '%)';
            ctx.stroke();

            ctx.beginPath();
            // draw the target for this firework with a pulsing circle
            ctx.arc(this.tx, this.ty, this.targetRadius, 0, Math.PI * 2);
            ctx.stroke();
        }

        // create particle
        function Particle(x, y) {
            this.x = x;
            this.y = y;
            // track the past coordinates of each particle to create a trail effect, increase the coordinate count to create more prominent trails
            this.coordinates = [];
            this.coordinateCount = 5;
            while (this.coordinateCount--) {
                this.coordinates.push([this.x, this.y]);
            }
            // set a random angle in all possible directions, in radians
            this.angle = random(0, Math.PI * 2);
            this.speed = random(1, 10);
            // friction will slow the particle down
            this.friction = 0.95;
            // gravity will be applied and pull the particle down
            this.gravity = 1;
            // set the hue to a random number +-20 of the overall hue variable
            this.hue = random(hue - 20, hue + 20);
            this.brightness = random(50, 80);
            this.alpha = 1;
            // set how fast the particle fades out
            this.decay = random(0.015, 0.03);
        }

        // update particle
        Particle.prototype.update = function (index) {
            // remove last item in coordinates array
            this.coordinates.pop();
            // add current coordinates to the start of the array
            this.coordinates.unshift([this.x, this.y]);
            // slow down the particle
            this.speed *= this.friction;
            // apply velocity
            this.x += Math.cos(this.angle) * this.speed;
            this.y += Math.sin(this.angle) * this.speed + this.gravity;
            // fade out the particle
            this.alpha -= this.decay;

            // remove the particle once the alpha is low enough, based on the passed in index
            if (this.alpha <= this.decay) {
                particles.splice(index, 1);
            }
        }

        // draw particle
        Particle.prototype.draw = function () {
            ctx.beginPath();
            // move to the last tracked coordinates in the set, then draw a line to the current x and y
            ctx.moveTo(this.coordinates[this.coordinates.length - 1][0], this.coordinates[this.coordinates.length - 1][1]);
            ctx.lineTo(this.x, this.y);
            ctx.strokeStyle = 'hsla(' + this.hue + ', 100%, ' + this.brightness + '%, ' + this.alpha + ')';
            ctx.stroke();
        }

        // create particle group/explosion
        function createParticles(x, y) {
            // increase the particle count for a bigger explosion, beware of the canvas performance hit with the increased particles though
            var particleCount = 30;
            while (particleCount--) {
                particles.push(new Particle(x, y));
            }
        }

        // main demo loop
        function loop() {
            // this function will run endlessly with requestAnimationFrame
            requestAnimFrame(loop);

            // increase the hue to get different colored fireworks over time
            hue += 0.5;

            // normally, clearRect() would be used to clear the canvas
            // we want to create a trailing effect though
            // setting the composite operation to destination-out will allow us to clear the canvas at a specific opacity, rather than wiping it entirely
            ctx.globalCompositeOperation = 'destination-out';
            // decrease the alpha property to create more prominent trails
            ctx.fillStyle = 'rgba(0, 0, 0, 0.5)';
            ctx.fillRect(0, 0, cw, ch);
            // change the composite operation back to our main mode
            // lighter creates bright highlight points as the fireworks and particles overlap each other
            ctx.globalCompositeOperation = 'lighter';

            // loop over each firework, draw it, update it
            var i = fireworks.length;
            while (i--) {
                fireworks[i].draw();
                fireworks[i].update(i);
            }

            // loop over each particle, draw it, update it
            var i = particles.length;
            while (i--) {
                particles[i].draw();
                particles[i].update(i);
            }

            // launch fireworks automatically to random coordinates, when the mouse isn't down
            if (timerTick >= timerTotal) {
                if (!mousedown) {
                    // start the firework at the bottom middle of the screen, then set the random target coordinates, the random y coordinates will be set within the range of the top half of the screen
                    fireworks.push(new Firework(cw / 2, ch, random(0, cw), random(0, ch / 2)));
                    timerTick = 0;
                }
            } else {
                timerTick++;
            }

            // limit the rate at which fireworks get launched when mouse is down
            if (limiterTick >= limiterTotal) {
                if (mousedown) {
                    // start the firework at the bottom middle of the screen, then set the current mouse coordinates as the target
                    fireworks.push(new Firework(cw / 2, ch, mx, my));
                    limiterTick = 0;
                }
            } else {
                limiterTick++;
            }
        }

        window.onload = function () {
            var merrywrap = document.getElementById("merrywrap");
            var box = merrywrap.getElementsByClassName("giftbox")[0];
            var step = 1;
            var stepMinutes = [500, 500, 200, 200];
            function init() {
                box.addEventListener("click", openBox, false);
            }
            function stepClass(step) {
                merrywrap.className = 'merrywrap';
                merrywrap.className = 'merrywrap step-' + step;
            }
            function openBox() {
                if (step === 1) {
                    box.removeEventListener("click", openBox, false);
                }
                stepClass(step);
                if (step === 3) {
                }
                if (step === 4) {
                    reveal();
                    return;
                }
                setTimeout(openBox, stepMinutes[step - 1]);
                step++;
            }

            init();

        }

        function reveal() {
            document.querySelector('.merrywrap').style.backgroundColor = 'transparent';

            loop();

            var w, h;
            if (window.innerWidth >= 1000) {
                w = 295; h = 185;
            }
            else {
                w = 255; h = 155;
            }

            var ifrm = document.createElement("iframe");
            ifrm.setAttribute("src", "https://www.youtube.com/embed/KDxJlW6cxRk?controls=0&loop=1&autoplay=1");
            //ifrm.style.width = `${w}px`;
            //ifrm.style.height = `${h}px`;
            ifrm.style.border = 'none';
            document.querySelector('#video').appendChild(ifrm);
        }
    </script>

<script>
    const balloonContainer = document.getElementById("balloon-container");

    function random(num) {
        return Math.floor(Math.random() * num);
    }

    function getRandomStyles() {
        var r = random(255);
        var g = random(255);
        var b = random(255);
        var mt = random(200);
        var ml = random(50);
        var dur = random(5) + 5;
        return `
background-color: rgba(${r},${g},${b},0.7);
color: rgba(${r},${g},${b},0.7); 
box-shadow: inset -7px -3px 10px rgba(${r - 10},${g - 10},${b - 10},0.7);
margin: ${mt}px 0 0 ${ml}px;
animation: float ${dur}s ease-in infinite
`;
    }

    function createBalloons(num) {
        for (var i = num; i > 0; i--) {
            var balloon = document.createElement("div");
            balloon.className = "balloon";
            balloon.style.cssText = getRandomStyles();
            balloonContainer.append(balloon);
        }
    }

    // function removeBalloons() {
    //     balloonContainer.style.opacity = 0;
    //     setTimeout(() => {
    //         balloonContainer.remove()
    //     }, 500)
    // }

    window.addEventListener("load", () => {
        createBalloons(30)
    });

    window.addEventListener("click", () => {
        removeBalloons();
    });

</script>

</body>

</html>
