response = Map();
response.put("action","reply");
response.put("replies",{{"text":"Hey! Welcome to my store! Ahh..well I own it when my human friends aren't around. So tell me, what brings you here?"}});
options = {"Great deals of the day","Need any help with purchasing?","Have a query?","Order Via Prescription"};
response.put("suggestions",options);
return response;
