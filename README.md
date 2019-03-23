# GCP
第19回勉強会　Google Cloud Platform を使ったセッション・ハンズオン

2019/03/23(土) 13:00 〜 16:30




AutoML

	最小各ラベル　10枚


	ラーメン次郎　5000枚　各店舗100枚

	月100枚　無料
	100枚毎に　1階層　35ドル


AWS　に比べて　GCP　の　優位性
	検証結果を見てみると精度は高い
	tensorflow なら　TPU　で　葉y各処理できる



AIzaSyCw23eoc5llu7XiXswZS61NZsqcdIgSjaQ



認証情報

 
有効な API にアクセスするための認証情報を作成します。詳細については、認証のドキュメント をご覧ください。

API キー
名前	作成日	制限事項	キー	
 API キー 1	2019/03/23	なし	AIzaSyCw23eoc5llu7XiXswZS61NZsqcdIgSjaQ 	 




コマンドを使って
有効化したAPIを一覧できる


video    API
Cloud Video Intelligence API




#@title 検出したオブジェクトをハイライトする関数 highlight_objects を定義

highlight_objects は　関数として定義している　コメントの裏に隠れていた。


from PIL import Image, ImageDraw

def highlight_objects(image_file, objects):
  image = Image.open(image_file)
  draw = ImageDraw.Draw(image, "RGBA")
  
  width = image.getbbox()[-2]
  height = image.getbbox()[-1]
  
  for object in objects:
    n_vertex_lt = tuple(object['boundingPoly']['normalizedVertices'][0].values())
    n_vertex_rb = tuple(object['boundingPoly']['normalizedVertices'][2].values())
    
    vertex_lt = (int(n_vertex_lt[0] * width), int(n_vertex_lt[1] * height))
    vertex_rb = (int(n_vertex_rb[0] * width), int(n_vertex_rb[1] * height))
    
    # bounding box
    draw.rectangle(xy=(vertex_lt, vertex_rb), outline='red')
    
    # probability
    object['name']
    draw.text(xy=(vertex_lt[0], vertex_lt[1]-10),
              text=object['name'] + ':' + str(format(object['score'], '.3f')),
              fill='red')    
  display(image)
  
  


言語　翻訳
　まず　文章から言語を解析してから　翻訳する
 
 
 
 質問
 
 　　和書分離できるか
   
   シングルソース　でもできるが　精度がまだ
   
   
   
   
 
 
 
