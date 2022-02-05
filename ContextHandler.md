response = Map();
info answers;
if(context_id.equals("greatdeals"))
{
	ans = answers.get("found").get("text");
	if(ans.containsIgnoreCase("Choose different%"))
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
	else if(ans.containsIgnoreCase("Not interested"))
	{
		response.put("action","end");
	}
	else if(ans.equalsIgnoreCase("1") || ans.equalsIgnoreCase("2") || ans.equalsIgnoreCase("3") || ans.equalsIgnoreCase("4"))
	{
		if(ans.equalsIgnoreCase("1"))
		{
			data = "T-shirts,jeans & more - Min 40 %";
		}
		else if(ans.equalsIgnoreCase("2"))
		{
			data = "Bean bags & more Extra 10% ";
		}
		else if(ans.equalsIgnoreCase("3"))
		{
			data = "Headphones & speakers";
		}
		else
		{
			data = "Four star dry irons upto 70% off";
		}
		response.put("action","context");
		response.put("context_id","productoption");
		questions = Collection();
		question1 = {"name":"option","replies":{{"text":data},{"text":"Great choice! Please share your phone number where I'll send you the promo code."}},"suggestions":{"Notify me later","Add to my wishlist","Add to my cart"}};
		questions.insert(question1);
		response.put("questions",questions);
	}
}
if(context_id.equals("productoption"))
{
	ans = answers.get("option").get("text");
	if(ans.containsIgnoreCase("Notify me later") || ans.containsIgnoreCase("Add to my wishlist") || ans.containsIgnoreCase("Add to my cart"))
	{
		response.put("action","end");
	}
	else
	{
		response.put("action","context");
		response.put("context_id","otherdeals");
		questions = Collection();
		question1 = {"name":"deals","replies":{{"text":"Thanks. Check your phone for the promo code.Happy shopping!"}},"input":{"type":"select","options":{"get another deal","Thank you"}}};
		questions.insert(question1);
		response.put("questions",questions);
	}
}
if(context_id.equals("otherdeals"))
{
	ans = answers.get("deals").get("text");
	if(ans.containsIgnoreCase("get another deal"))
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
	else
	{
		response.put("action","end");
	}
}
if(context_id.equals("helppurchasing"))
{
	ans = answers.get("buy").get("text");
	if(ans.containsIgnoreCase("Cold,Cough"))
	{
		response.put("action","context");
		response.put("context_id","Cold,Cough");
		questions = Collection();
		question1 = {"name":"budget","replies":{{"text":"Nice.Do you have budget in mind?"}},"input":{"type":"select","options":{"Below $5000","$5000-$10000","Above $10000","Show all"}}};
		question2 = {"name":"search","replies":{{"text":"I'm searching the entire store.Phew...It's tiring.Do humans get tired too? just curious"},{"text":"Ok,here is some good stuff that I found"},{"text":"1.Cofsils Lozenges Lemon Ginger - ₹32","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p2_i1_w690.png?width=640"},{"text":"2.Vicks Vaporub 50ml - ₹78","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p1_i1_w450.jpeg"},{"text":"3.Nasivion Classic Adult 0.05% Nasal Spray - ₹78","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p3_i3_w690.png?width=640"},{"text":"4.Himalaya Koflet-H Lozenges Ginger - ₹23","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p9_i2_w690.png?width=160"},{"text":"Select from given options"}},"input":{"type":"select","options":{"1","2","3","4"}}};
		questions.insert(question1);
		questions.insert(question2);
		response.put("questions",questions);
	}
	else if(ans.containsIgnoreCase("Fever,Flue"))
	{
		response.put("action","context");
		response.put("context_id","Fever,Flue");
		questions = Collection();
		question1 = {"name":"budget","replies":{{"text":"Nice.Do you have budget in mind?"}},"input":{"type":"select","options":{"Below $5000","$5000-$10000","Above $10000","Show all"}}};
		question2 = {"name":"search","replies":{{"text":"Give me a moment while I hunt for some really cool stuff for you"},{"text":"Here are some of the things I've picked up. Do you like any of these?"},{"text":"1.Digital Thermometer- ₹201","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p13_i5_w690.png?width=160"},{"text":"2 Dolo 650 Tablet ₹27","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p6_i2_w690.png?width=160"},{"text":"3.Crocin Pain Relief Tablet - ₹68","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p5_i4_w690.png?width=160"},{"text":"4.Saridon Headache Relief Tablet - ₹23","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p4_i2_w690.png?width=160"},{"text":"Select from given options"}},"input":{"type":"select","options":{"1","2","3","4"}}};
		questions.insert(question1);
		questions.insert(question2);
		response.put("questions",questions);
	}
	else if(ans.containsIgnoreCase("COVID Care,COVID Protection"))
	{
		response.put("action","context");
		response.put("context_id","COVID Care , COVID Protection");
		questions = Collection();
		question1 = {"name":"budget","replies":{{"text":"Nice.Do you have budget in mind?"}},"input":{"type":"select","options":{"Below ₹10-₹100","₹100-₹300","Above ₹300","Show all"}}};
		question2 = {"name":"search","replies":{{"text":"Give me a moment while I hunt for some really cool stuff for you"},{"text":"Here are some of the things I've picked up. Do you like any of these?"},{"text":"1.Disposable PPE Kit -₹209","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p12_i2_w548.jpeg"},{"text":"2.Control D 3 Reusable Face Shield- ₹244","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p11_i5_w690.png?width=640"},{"text":"3.Dettol Instant Hand Sanitizer - Original 50 ml- ₹15","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p10_i1_w600.jpeg"},{"text":"4.White KN95 Face Mask - ₹136","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p7_i3_w376.jpeg"},{"text":"Select from given options"}},"input":{"type":"select","options":{"1","2","3","4"}}};
		questions.insert(question1);
		questions.insert(question2);
		response.put("questions",questions);
	}
	else if(ans.containsIgnoreCase("Show all categories"))
	{
		response.put("action","context");
		response.put("context_id","showall");
		questions = Collection();
		question1 = {"name":"budget","replies":{{"text":"Nice.Do you have budget in mind?"}},"input":{"type":"select","options":{"Below ₹10-₹100","₹100-₹300","Above ₹300","Show all"}}};
		question2 = {"name":"search","replies":{{"text":"Give me a moment while I hunt for some really cool stuff for you"},{"text":"Here are some of the things I've picked up. Do you like any of these?"},{"text":"COVID Care,COVID Protection"},{"text":"1.Disposable PPE Kit -₹209","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p12_i2_w548.jpeg"},{"text":"2.Control D 3 Reusable Face Shield- ₹244","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p11_i5_w690.png?width=640"},{"text":"3.Dettol Instant Hand Sanitizer - Original 50 ml- ₹15","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p10_i1_w600.jpeg"},{"text":"4.White KN95 Face Mask - ₹136","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p7_i3_w376.jpeg"},{"text":"Cold,Cough"},{"text":"5.Cofsils Lozenges Lemon Ginger - ₹32","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p2_i1_w690.png?width=640"},{"text":"6.Vicks Vaporub 50ml - ₹78","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p1_i1_w450.jpeg"},{"text":"7.Nasivion Classic Adult 0.05% Nasal Spray - ₹78","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p3_i3_w690.png?width=640"},{"text":"8.Himalaya Koflet-H Lozenges Ginger - ₹23","image":"https://hellomedico.weebly.com/uploads/1/4/0/5/140525464/s534491701160467043_p9_i2_w690.png?width=160"},{"text":"Select from given options"},{"text":"Select from given options"}},"input":{"type":"select","options":{"1","2","3","4","5","6","7","8"}}};
		questions.insert(question1);
		questions.insert(question2);
		response.put("questions",questions);
	}
	else
	{
		response.put("action","context");
		response.put("context_id","helppurchasing");
		questions = Collection();
		question1 = {"name":"buy","replies":{{"text":"I can definitely help you with that.Tell me what do you want to buy?"}},"suggestions":{"Cold,Cough","Fever,Flue","Covid Care,COVID Protection","Show all categories"}};
		questions.insert(question1);
		response.put("questions",questions);
	}
}
if(context_id.equals("showall"))
{
	ans = answers.get("search").get("text");
	if(ans.equalsIgnoreCase("1"))
	{
		data = "Disposable PPE Kit ₹209";
	}
	else if(ans.equalsIgnoreCase("2"))
	{
		data = "Control D 3 Reusable Face Shield ₹24";
	}
	else if(ans.equalsIgnoreCase("3"))
	{
		data = "Dettol Instant Hand Sanitizer - Original 50 ml ₹15";
	}
	else if(ans.equalsIgnoreCase("4"))
	{
		data = "White KN95 Face Mask  ₹136";
	}
	else if(ans.equalsIgnoreCase("5"))
	{
		data = "Cofsils Lozenges Lemon Ginger  ₹32";
	}
	else if(ans.equalsIgnoreCase("6"))
	{
		data = "Vicks Vaporub 50ml  ₹78";
	}
	else if(ans.equalsIgnoreCase("7"))
	{
		data = "Nasivion Classic Adult 0.05% Nasal Spray  ₹78";
	}
	else
	{
		data = "Himalaya Koflet-H Lozenges Ginger  ₹23";
	}
	response.put("action","context");
	response.put("context_id","search");
	questions = Collection();
	question1 = {"name":"delivery","replies":{{"text":data},{"text":"Wow! That's a great choice " + data},{"text":"Select delivery option or go for another product"}},"input":{"type":"select","options":{"choose a location","currentlocation","other products"}}};
	questions.insert(question1);
	response.put("questions",questions);
}
if(context_id.equals("COVID Care , COVID Protection"))
{
	ans = answers.get("search").get("text");
	if(ans.equalsIgnoreCase("1"))
	{
		data = "Disposable PPE Kit- ₹209";
	}
	else if(ans.equalsIgnoreCase("2"))
	{
		data = "Control D 3 Reusable Face Shield- ₹244";
	}
	else if(ans.equalsIgnoreCase("3"))
	{
		data = "Dettol Instant Hand Sanitizer - Original 50 ml- ₹15";
	}
	else
	{
		data = "White KN95 Face Mask- ₹136";
	}
	response.put("action","context");
	response.put("context_id","search");
	questions = Collection();
	question1 = {"name":"delivery","replies":{{"text":data},{"text":"Wow! That's a great choice " + data},{"text":"Select delivery option or go for another product"}},"input":{"type":"select","options":{"choose a location","currentlocation","other products"}}};
	questions.insert(question1);
	response.put("questions",questions);
}
if(context_id.equals("Fever,Flue"))
{
	ans = answers.get("search").get("text");
	if(ans.equalsIgnoreCase("1"))
	{
		data = "Digital Thermometer- ₹201";
	}
	else if(ans.equalsIgnoreCase("2"))
	{
		data = "Dolo 650 Tablet- ₹27";
	}
	else if(ans.equalsIgnoreCase("3"))
	{
		data = "Crocin Pain Relief Tablet - ₹68";
	}
	else
	{
		data = "Saridon Headache Relief Tablet - ₹23";
	}
	response.put("action","context");
	response.put("context_id","search");
	questions = Collection();
	question1 = {"name":"delivery","replies":{{"text":data},{"text":"Wow! That's a great choice " + data},{"text":"Select delivery option or go for another product"}},"input":{"type":"select","options":{"choose a location","currentlocation","other products"}}};
	questions.insert(question1);
	response.put("questions",questions);
}
if(context_id.equals("Cold,Cough"))
{
	ans = answers.get("search").get("text");
	if(ans.equalsIgnoreCase("1"))
	{
		data = "Cofsils Lozenges Lemon Ginger - ₹32";
	}
	else if(ans.equalsIgnoreCase("2"))
	{
		data = "Vicks Vaporub 50ml - ₹78";
	}
	else if(ans.equalsIgnoreCase("3"))
	{
		data = "Nasivion Classic Adult 0.05% Nasal Spray - ₹78";
	}
	else
	{
		data = "Himalaya Koflet-H Lozenges Ginger - ₹23";
	}
	response.put("action","context");
	response.put("context_id","search");
	questions = Collection();
	question1 = {"name":"delivery","replies":{{"text":data},{"text":"Wow! That's a great choice " + data},{"text":"Select delivery option or go for another product"}},"input":{"type":"select","options":{"choose a location","currentlocation","other products"}}};
	questions.insert(question1);
	response.put("questions",questions);
}
if(context_id.equals("search"))
{
	ans = answers.get("delivery").get("text");
	if(ans.containsIgnoreCase("choose a location"))
	{
		response.put("action","context");
		response.put("context_id","deliverylocation");
		questions = Collection();
		question1 = {"name":"address","replies":{"Please choose an address and confirm the delivery location",{"text":"1. Chennai-Zoho Corporation Pvt. Ltd., Estancia IT Park, Plot No. 140 & 151, GST Road, Vallancherry Village, Chengalpattu Taluk, Kanchipuram District 603 202, INDIA"},{"text":" 2.Tenkasi - Zoho Technologies Pvt. Ltd., Silaraipuravu Village, Mathalamparai, Tenkasi, Tirunelveli District 627 814, INDIA "},{"text":"3.Renigunta - Zoho Technologies Pvt. Ltd., 16-237, Srikalahasti Road, Renigunta Pillapalem, Renigunta, Andhra Pradesh, 517520, INDIA."},{"text":"Choose address"}},"input":{"type":"select","options":{"1","2","3"}}};
		questions.insert(question1);
		response.put("questions",questions);
	}
	else if(ans.containsIgnoreCase("currentlocation"))
	{
		response.put("action","context");
		response.put("context_id","currentlocation");
		questions = Collection();
		question2 = {"name":"address","replies":{{"text":"Address located"}},"input":{"type":"location","lat":"12.844037","lng":"80.060411","label":"Pick a location","radius":"2 kms"}};
		questions.insert(question2);
		response.put("questions",questions);
	}
	else
	{
		response.put("action","context");
		response.put("context_id","helppurchasing");
		questions = Collection();
		question1 = {"name":"buy","replies":{{"text":"I can definitely help you with that.Tell me what do you want to buy?"}},"suggestions":{"Mobiles,Computers","Sports,Fitness,Bags,Luggage","TV,Appliances,Electronics","Show all categories"}};
		questions.insert(question1);
		response.put("questions",questions);
	}
}
if(context_id.equals("currentlocation"))
{
	data = answers.get("address").get("text");
	response.put("action","context");
	response.put("context_id","currentaddress");
	questions = Collection();
	question1 = {"name":"pay","replies":{{"text":"It will be delivered to the given address " + data}},"input":{"type":"select","options":{"make payment","select other"}}};
	questions.insert(question1);
	response.put("questions",questions);
}
if(context_id.equals("currentaddress"))
{
	ans = answers.get("pay").get("text");
	if(ans.containsIgnoreCase("make payment"))
	{
		response.put("action","reply");
		response.put("replies",{{"text":"Payment success"},{"text":"Your order has been placed successfully."}});
		response.put("input",{"type":"select","options":{"Continue shopping"}});
	}
	else
	{
		response.put("action","context");
		response.put("context_id","currentlocation");
		questions = Collection();
		question2 = {"name":"address","replies":{{"text":"Address located"}},"input":{"type":"location","lat":"12.844037","lng":"80.060411","label":"Pick a location","radius":"2 kms"}};
		questions.insert(question2);
		response.put("questions",questions);
	}
}
if(context_id.equals("deliverylocation"))
{
	ans = answers.get("address").get("text");
	if(ans.equalsIgnoreCase("1"))
	{
		data = "Chennai-Zoho Corporation Pvt. Ltd., Estancia IT Park, Plot No. 140 & 151, GST Road, Vallancherry Village, Chengalpattu Taluk, Kanchipuram District 603 202, INDIA";
	}
	else if(ans.equalsIgnoreCase("2"))
	{
		data = "Tenkasi - Zoho Technologies Pvt. Ltd., Silaraipuravu Village, Mathalamparai, Tenkasi, Tirunelveli District 627 814, INDIA ";
	}
	else
	{
		data = "Renigunta - Zoho Technologies Pvt. Ltd., 16-237, Srikalahasti Road, Renigunta Pillapalem, Renigunta, Andhra Pradesh, 517520, INDIA.";
	}
	response.put("action","context");
	response.put("context_id","deliveryadd");
	questions = Collection();
	question1 = {"name":"deliveryaddress","replies":{{"text":"It will be delivered to the given address " + data}},"input":{"type":"select","options":{"make payment","select other"}}};
	questions.insert(question1);
	response.put("questions",questions);
}
if(context_id.equals("deliveryadd"))
{
	ans = answers.get("deliveryaddress").get("text");
	if(ans.containsIgnoreCase("make payment"))
	{
		response.put("action","reply");
		response.put("replies",{{"text":"Payment success"},{"text":"Your order has been placed successfully."}});
		response.put("input",{"type":"select","options":{"Continue shopping"}});
	}
	else
	{
		response.put("action","context");
		response.put("context_id","deliverylocation");
		questions = Collection();
		question1 = {"name":"address","replies":{"Please choose an address and confirm the delivery location",{"text":"1. Chennai-Zoho Corporation Pvt. Ltd., Estancia IT Park, Plot No. 140 & 151, GST Road, Vallancherry Village, Chengalpattu Taluk, Kanchipuram District 603 202, INDIA"},{"text":" 2.Tenkasi - Zoho Technologies Pvt. Ltd., Silaraipuravu Village, Mathalamparai, Tenkasi, Tirunelveli District 627 814, INDIA "},{"text":"3.Renigunta - Zoho Technologies Pvt. Ltd., 16-237, Srikalahasti Road, Renigunta Pillapalem, Renigunta, Andhra Pradesh, 517520, INDIA."},{"text":"Choose address"}},"input":{"type":"select","options":{"1","2","3"}}};
		questions.insert(question1);
		response.put("questions",questions);
	}
}
if(context_id.equals("query"))
{
	ans = answers.get("help").get("text");
	if(ans.containsIgnoreCase("Order status"))
	{
		response.put("action","reply");
		replies = Collection();
		replies.insert({"text":"Here is the list of items which is yet to be delivered."});
		replies.insert({"text":"Fila Men's Ristoro Brown and Beige...-Ordered on 5-sept-2016","image":"https://cdnd.lystit.com/520/650/n/photos/tillys/5d9c4472/fila-REDCO-Mindbender-F-Mens-Shoes.jpeg"});
		replies.insert({"text":"Fila Men's Farli Walk Plus 2 Camel...-Ordered on 5-sept-2016","image":"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSXUFc8VzVd5CEyjpMMt_rtwebkf8Ni1tVIipJHrg8aP9WnvsVH"});
		replies.insert({"text":"Change by design-Ordered on 26-aug-2016","image":"https://cityofwater.files.wordpress.com/2011/11/cbd_2_626px.jpg"});
		replies.insert({"text":"The Practitioner's Guide to User...-Ordered on 26-aug-2016","image":"https://media.karousell.com/media/photos/products/2016/08/07/the_practitioners_guide_to_user_experience_design_book_the_practitioners_guide_to_user_experience_de_1470584012_8ac3be01.jpg"});
		response.put("input",{"type":"select","options":{"Thanks","Keep shopping"}});
		response.put("replies",replies);
	}
	else if(ans.containsIgnoreCase("Refund not received"))
	{
		response.put("action","reply");
		replies = Collection();
		replies.insert({"text":"Let me get the refund policies."});
		replies.insert({"text":"Returns,Refunds & Replacements"});
		replies.insert({"text":"Return Items you ordered"});
		replies.insert({"text":"Return items fulfilled by amazon"});
		replies.insert({"text":"Return seller fulfilled items"});
		replies.insert({"text":"Return a gift"});
		replies.insert({"text":"Track your return"});
		replies.insert({"text":"About our return policies"});
		replies.insert({"text":"About return shipping"});
		replies.insert({"text":"Items that can't be returned"});
		replies.insert({"text":"Return Documentation"});
		replies.insert({"text":"Return gift cards"});
		response.put("input",{"type":"select","options":{"Thanks","Keep shopping","Connect with agent"}});
		response.put("replies",replies);
	}
	else if(ans.containsIgnoreCase("Received a wrong item"))
	{
		response.put("action","context");
		response.put("context_id","wrongitem");
		questions = Collection();
		question1 = {"name":"list","replies":{{"text":"Here is the list of items that were delivered to you. Please choose those item that you would like to return."},{"text":"1.Fila Men's Ristoro Brown and Beige...-Ordered on 5-sept-2016","image":"https://cdnd.lystit.com/520/650/n/photos/tillys/5d9c4472/fila-REDCO-Mindbender-F-Mens-Shoes.jpeg"},{"text":"2 Fila Men's Farli Walk Plus 2 Camel...-Ordered on 5-sept-2016","image":"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSXUFc8VzVd5CEyjpMMt_rtwebkf8Ni1tVIipJHrg8aP9WnvsVH"},{"text":"3.Change by design-Ordered on 26-aug-2016","image":"https://cityofwater.files.wordpress.com/2011/11/cbd_2_626px.jpg"},{"text":"4.The Practitioner's Guide to User...-Ordered on 26-aug-2016","image":"https://media.karousell.com/media/photos/products/2016/08/07/the_practitioners_guide_to_user_experience_design_book_the_practitioners_guide_to_user_experience_de_1470584012_8ac3be01.jpg"},{"text":"Select from above options"}},"input":{"type":"select","options":{"1","2","3","4","Connect with agent"}}};
		questions.insert(question1);
		response.put("questions",questions);
	}
	else if(ans.containsIgnoreCase("Connect with agent"))
	{
		response.put("action","end");
	}
	else
	{
		response.put("action","context");
		response.put("context_id","query");
		questions = Collection();
		question1 = {"name":"help","replies":{{"text":"What is it that you need help with?"}},"suggestions":{"Order status","Refund not received","Received a wrong item","Connect with agent"}};
		questions.insert(question1);
		response.put("questions",questions);
	}
}
if(context_id.equals("wrongitem"))
{
	ans = answers.get("list").get("text");
	if(ans.equalsIgnoreCase("1") || ans.equalsIgnoreCase("2") || ans.equalsIgnoreCase("3") || ans.equalsIgnoreCase("4"))
	{
		if(ans.equalsIgnoreCase("1"))
		{
			data = "Fila Men's Ristoro Brown and Beige...-Ordered on 5-sept-2016";
		}
		else if(ans.equalsIgnoreCase("2"))
		{
			data = "Fila Men's Farli Walk Plus 2 Camel...-Ordered on 5-sept-2016";
		}
		else if(ans.equalsIgnoreCase("3"))
		{
			data = "Change by design-Ordered on 26-aug-2016";
		}
		else if(ans.equalsIgnoreCase("4"))
		{
			data = "The Practitioner's Guide to User...-Ordered on 26-aug-2016";
		}
		response.put("action","reply");
		response.put("replies",{{"text":data},{"text":"We are sorry for the inconvenience caused. Your refund has been scheduled. The funds will be credited in 7 working days."}});
		response.put("input",{"type":"select","options":{"Thanks","Keep shopping"}});
	}
	else
	{
		response.put("action","end");
	}
}
if(context_id.equals("justbrowsing"))
{
	ans = answers.get("deal").get("text");
	if(ans.containsIgnoreCase("Deals"))
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
	else
	{
		response.put("action","context");
		response.put("context_id","notify");
		questions = Collection();
		question1 = {"name":"email","replies":{{"text":"Where can I drop an email with all exciting offers? Please share your email address."}}};
		questions.insert(question1);
		response.put("questions",questions);
	}
}
if(context_id.equals("notify"))
{
	response.put("action","end");
	response.put("replies",{{"text":"Thank you.The offer list with the promo codes is on it's way! Happy shopping!"}});
}
return response;
