# surfs_up

## 1. Overiview of the statistical analysis:

This analysis aims to gather information about temperature trends before opening the surf and ice cream shop, focusing on June and December, to determine if the shop is sustainable year-round. 

## 2. Results: 

- The mean temperature in June is 74.9 deg. F, a min. of 64 and a max. of 85 deg. F. 
- The mean temperature in December is 71.0 deg. F, with a min of 56 and a max. of 83 deg. F. 
- The mean temperatures for June and December are similar. 
- December has colder days than June (with a mim. of 10 deg. F colder).  

#### June Temps.
![Screen Shot 2022-09-22 at 12 56 00 PM](https://user-images.githubusercontent.com/108419097/191807128-18098470-3f01-4205-a734-9814341a2b09.png)

#### December Temps.
![Screen Shot 2022-09-22 at 12 55 25 PM](https://user-images.githubusercontent.com/108419097/191807012-04fb7a6f-ecd9-408e-bb46-af895b94e3e3.png)

## 3. Summary: 

Overall, the temperatures in June are warmer than in December by 4 deg. F.  December may have less business, but not by much.  In addition to the temperature, we also need to consider rainning, another factor that will affect outdoor business. 

#### Two queries:

1. June - examine both precipitation and temp

       # extracts date, precipitation, and temperature for the month of june 
       june_prcp = session.query(Measurement.date, Measurement.prcp, Measurement.tobs).filter(
           extract('month', Measurement.date) == 6).all()
       print(june_prcp)
       
       # df
       june_prcp = pd.DataFrame(june_prcp, columns=['date','precipitation','tobs' ])
       print(june_prcp)
       
       # drop index
       print(june_prcp.to_string(index=False))
       
       # plot
       june_prcp.plot()
       plt.title('June')
       plt.tight_layout()

#### June - precipitation and temperature

![Screen Shot 2022-09-22 at 2 15 40 PM](https://user-images.githubusercontent.com/108419097/191821541-2b0a1a86-006f-4b2c-b3f0-902b63b65bc3.png)
 
2. December - examine both precipitation and temp

       # extracts date, precipitation, and temperature for the month of dec 
       dec_prcp = session.query(Measurement.date, Measurement.prcp, Measurement.tobs).filter(
           extract('month', Measurement.date) == 12).all()
       print(dec_prcp)
       
       # df
       dec_prcp = pd.DataFrame(dec_prcp, columns=['date','precipitation','tobs' ])
       print(dec_prcp)
       
       # drop index
       print(dec_prcp.to_string(index=False))
       
       # plot
       dec_prcp.plot()
       plt.title('December')
       plt.tight_layout()


#### December - precipitation and temperature

![Screen Shot 2022-09-22 at 2 19 42 PM](https://user-images.githubusercontent.com/108419097/191822246-8332f4b9-2d39-4c0a-824b-65e9a2f90cec.png)
