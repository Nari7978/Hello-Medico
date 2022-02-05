response = Map();
if(operation.equals("chat"))
{
	// First question from visitor
	response.put("action","reply");
	response.put("replies",{{"text":"Hey! Welcome to my store! Ahh..well I own it when my human friends aren't around. So tell me, what brings you here?"}});
	options = {"Great deals of the day","Need any help with purchasing?","Have a query?","Order Via Prescription"};
	response.put("suggestions",options);
}
else if(operation.equals("message"))
{
	msg = message.get("text");
	if(msg.containsIgnoreCase("Great deals of the day"))
	{
		response.put("action","context");
		response.put("context_id","greatdeals");
		questions = Collection();
		question1 = {"name":"greatdeals","replies":{{"text":"You got lucky! I have a number of exciting offers for you. Tell me what % discounts are you looking for? It will help me show you the best results."}},"input":{"type":"slider","values":{"0","10","20","30","70"}}};
		question2 = {"name":"found","replies":{{"text":"I found products you can choose from given options"},{"text":"1. T-shirts,jeans & more-Min 40% + Extra 10% off UCB,Lee...","image":"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSd1iHZzkvhYxba0rWl4T9lj-tgEw4od7__pCtZcjXAW4FrdDzd"},{"text":"2. Bean Bags & More Extra 10% off Budget Friendly Furniture","image":"https://5.imimg.com/data5/PE/AS/MY-37550917/gabbroo-bean-bag-brown-500x500.jpeg"},{"text":"3. Headphones & Speakers From ₹449 F&D,SkullCandy,JVC...","image":"https://azcd.harveynorman.com.au/media/catalog/product/cache/21/image/992x558/9df78eab33525d08d6e5fb8d27136e95/b/a/barrel-xl-3696432.jpg"},{"text":"4. Four Star Dry Irons- upto 70% off From ₹299","image":"https://images-na.ssl-images-amazon.com/images/I/71JWeBjxWGL._SX425_.jpg"},{"text":"Choose a different products or go for given mentioned options"}},"input":{"type":"select","options":{"Choose different%","Not interested","1","2","3","4"}}};
		questions.insert(question1);
		questions.insert(question2);
		response.put("questions",questions);
	}
	else if(msg.containsIgnoreCase("Need any help with purchasing?"))
	{
		response.put("action","context");
		response.put("context_id","helppurchasing");
		questions = Collection();
		question1 = {"name":"buy","replies":{{"text":"I can definitely help you with that.Tell me what do you want to buy?"}},"suggestions":{"Cold,Cough","Fever,Flue","COVID Care,COVID Protection","Show all categories"}};
		questions.insert(question1);
		response.put("questions",questions);
	}
	else if(msg.containsIgnoreCase("Have a query?"))
	{
		response.put("action","context");
		response.put("context_id","query");
		questions = Collection();
		question1 = {"name":"help","replies":{{"text":"What is it that you need help with?"}},"suggestions":{"Order status","Refund not received","Received a wrong item","Connect with agent"}};
		questions.insert(question1);
		response.put("questions",questions);
	}
	else if(msg.containsIgnoreCase("Order Via Prescription"))
	{
		response.put("action","context");
		response.put("context_id","Order Via Prescription");
		questions = Collection();
		question1 = {"name":"deal","replies":{{"text":"Please Upload the Prescription, :)"}}};
		questions.insert(question1);
		response.put("questions",questions);
	}
	else if(msg.equalsIgnoreCase("Thanks"))
	{
		response.put("action","end");
		response.put("replies",{{"text":"You 're welcome.Have a great day!"}});
	}
	else if(msg.equalsIgnoreCase("Keep shopping"))
	{
		response.put("action","context");
		response.put("context_id","helppurchasing");
		questions = Collection();
		question1 = {"name":"buy","replies":{{"text":"I can definitely help you with that.Tell me what do you want to buy?"}},"suggestions":{"Cold,Cough","Fever,Flue","COVID Care,COVID Protection","Show all categories"}};
		questions.insert(question1);
		response.put("questions",questions);
	}
	else if(msg.equalsIgnoreCase("Connect with agent"))
	{
		response.put("action","end");
	}
	else if(msg.equalsIgnoreCase("Continue shopping"))
	{
		response.put("action","end");
	}
	else
	{
		response.put("action","reply");
		response.put("replies",{{"text":"Hey! Welcome to my store! Ahh..well I own it when my human friends aren't around. So tell me, what brings you here?"}});
		options = {"Great deals of the day","Need any help with purchasing?","Have a query?","Just browsing"};
		response.put("suggestions",options);
	}
}
return response;
