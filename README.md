# SET-RANDOM-AMOUNT-OVER-PURCHASED-VEHICLES.

1.In server_publishVehicle2.sqf Find:


if(DZE_TRADER_SPAWNMODE) then {


above paste:
 
//CUSTOM FOR PURCHASED VEHICLES
if (DZE_UseCustomPurchasedVehicles) then {
    if (typeOf _object in PurchasedCheapCars) then {
    _fuel = (random((DZE_SetFuel_ForAllPurchasedVehicles select 1) - (DZE_SetFuel_ForAllPurchasedVehicles select 0)) + (DZE_SetFuel_ForAllPurchasedVehicles select 0)) / 100;
    //_dam  = (random((DZE_SetDamage_PurchasedCheapCars select 1) - (DZE_SetDamage_PurchasedCheapCars select 0)) + (DZE_SetDamage_PurchasedCheapCars select 0)) / 100; 
    //_object setHit ["karoserie", _dam];
    //_object setDamage _dam;
    }else{
    _fuel = (random((DZE_SetFuel_ForAllPurchasedVehicles select 1) - (DZE_SetFuel_ForAllPurchasedVehicles select 0)) + (DZE_SetFuel_ForAllPurchasedVehicles select 0)) / 50;
    };
    _object setfuel _fuel;
    };
//CUSTOM FOR PURCHASED VEHICLES



2. Open configvariables.sqf and at verytop paste:
//PURCHASED VEHICLES
DZE_UseCustomPurchasedVehicles = true; //false to disallow and spawn purchased vehicles with no damage and full of fuel.
PurchasedCheapCars = [
"tractor","SkodaBlue","SkodaGreen","SkodaRed","VolhaLimo_TK_CIV_EP1","Volha_1_TK_CIV_EP1","Volha_2_TK_CIV_EP1",
"VWGolf","car_hatchback","car_sedan","GLT_M300_LT","GLT_M300_ST","Lada1","Lada1_TK_CIV_EP1","Lada2","Lada2_TK_CIV_EP1","LadaLM"
];
DZE_SetFuel_ForAllPurchasedVehicles= [8,15];//[MIN,MAX];//HIGH VALUES MORE FUEL// Example: [8/100 = 0.08 fuel] [15/100 = 0.15 fuel] where 1 = full fuel// Vehicle listed divide by 100. The others by /50.
