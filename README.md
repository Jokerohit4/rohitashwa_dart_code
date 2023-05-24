# rohitashwa_dart_code


void main() {
  
   List<Map<String, dynamic>> jsonData = [
    {
      "id": "0001",
      "type": "donut",
      "name": "Cake",
      "ppu": 0.55,
      "batters": {
        "batter": [
          {"id": "1001", "type": "Regular"},
          {"id": "1002", "type": "Chocolate"},
          {"id": "1003", "type": "Blueberry"}
        ]
      },
      "topping": [
        {"id": "5001", "type": "None"},
        {"id": "5002", "type": "Glazed"},
        {"id": "5005", "type": "Sugar"},
        {"id": "5007", "type": "Powdered Sugar"}
      ]
    },
    {
      "id": "0002",
      "type": "donut",
      "name": "Cake",
      "ppu": 0.55,
      "batters": {
        "batter": [
          {"id": "1001", "type": "Blueberry"}
        ]
      },
      "topping": [
        {"id": "5001", "type": "None"},
        {"id": "5002", "type": "Glazed"}
      ]
    }
  ];
  
  
  
   print("ID\tType\tName\tPPU\tBatter Type\tTopping Type");
    
    // Loop through each item in the jsonData list
    for (var item in jsonData) {
      // Get the values for each column
      var id = item["id"];
      var type = item["type"];
      var name = item["name"];
      var ppu = item["ppu"];
      var toppings = item['topping'].map((topping) => topping['type']).join(", ");
        // Print the values in a formatted string
      for(int i = 0; i<item["batters"]["batter"].length;i++){
        var batterType = item["batters"]["batter"][i]["type"];
         print("$id\t$type\t$name\t$ppu\t$batterType \t$toppings");
      } 
    }
}
