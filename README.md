jquery.fasttap
==============

モバイル端末でのclickイベントをtouchイベントに変えたもの


使い方
--------------

html
```
<body>
	<a>link</a>
</body>
```

javascript
```
//documentにfasttapイベントを発火するようにする
//第一引数でfmoveイベントの発火感覚を指定する
  $(document).fasttap(50);

//タッチでイベント発行
  $(document).on("fstart","a",function(e){
    console.log("touchstart event");
  });

//タッチを離したときイベント発行
  $(document).on("ftap","a",function(e){
    console.log("touchend based click event");
  });

//長押しでイベント発行
  $(document).on("fhold","a",function(e){
    console.log("hold event");
  });

//タッチしたまま移動したときにイベント発行
  $(document).on("fmove","a",function(e){
    console.log("fmove event");
  });
```


特徴
--------------
非常にシンプルなのが特徴です  
fasttapのイベントでは、タッチ位置の座標を取得することができます  
```
  $(document).on("ftap","a",function(e,tapInfo){
    console.log(tapInfo.ftapTarget);
    console.log(tapInfo.startX);
    console.log(tapInfo.startY);
    console.log(tapInfo.endX);
    console.log(tapInfo.endY);
    console.log(tapInfo.moveX);
    console.log(tapInfo.moveY);
  });
```

backboneなどのフレームワークでも使用できます
```
  events:{
    "ftap":
  }
```

ライセンス
--------------
MIT ライセンス


