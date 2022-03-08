# ohiohydrologyMLR
To get specfic parameter values for model equations type in:
summary(V_MLR.5),
summary(Q_MLR.6),
summary(Q_MLR.8),
and run each separately.

All inputs to the model should be in metric units:
Rain fall depth - mm,
Watershed area - ha,
Average rain intenstity - mm/hr,
Peak rain intensity - mm/hr,
Slope and imperviousness inputs are in percent,
Only land uses used in the paper can be input into any model,

Inputs to the volume model include: "Rain.Depth.mm", "Area.ha", "Land.Use", and "Imperviousness,.percent". Predicted runoff volume is in cubic meters^(1/3).
#example: type in code#
predict(V_MLR.6,newdata=data.frame(Rain.Depth.mm=14.732, Area.ha=18.939305, Land.Use="SFR", Imperviousness.percent=45), interval="confidence")
#model output#
      fit      lwr      upr
1 7.01787 6.598405 7.437334



Inputs to peak flow model include: "Peak.5.int.mm.hr", "Rain.Depth.mm", "Area.ha", "Slope.percent", "Land.Use", and "Avg.Int.mm.hr". Use only the peak 5-minute rainfall intensity in Q_MLR.6 and only the average rainfall intensity in Q_MLR.8. Predicted peak flow rates are in cubic meters per second^(1/3).
#example: type in code#
predict(Q_MLR.5,newdata=data.frame(Peak.5.int.mm.hr=9.144, Rain.Depth.mm=14.732, Area.ha=18.939305, Slope.percent=1.1, Land.Use="SFR"), interval="confidence")
#model output#
        fit       lwr      upr
1 0.3777327 0.3510074 0.404458
