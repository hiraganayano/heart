# heart
My heart rate
from flask import Flask, jsonify, request
app = Flask(__name__)

heart = [

	{
		"heart_id" : "17",
		"date" : "October 2, 2022",
		"heart_rate" : "60/100",
		"name" : "Yano,Ervin C."

	}
]

@app.route ('/heart', methods= ['GET'])
def getHeart():
    return jsonify(heart)


@app.route ('/heart', methods= ['POST'])
def addHeart():
	heart = request.get_json()
	heart.append(heart)
	return{'id': len(heart)},200

@app.route('/movies/<int:index>' , methods= ['DELETE'])
def deleteHeart(index):
	heart.pop(index)
	return 'Record was deleted', 200

if __name__ == '__main__' :
    app.run()
