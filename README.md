Data Visualization techniques using codes
   library(ggplot2)
 
     ggplot(Tolu_project_data, aes(x = Booking_status))+
       geom_bar(fill = "Red", color = "black") +
        labs(x = "Booking Status", y = "Frequency",
          title = " Total Number of Bookings by Status")
     
     ggplot(Tolu_project_data, aes(x = Hotel_Name))+
       geom_bar(fill = "Green", color = "black") +
       labs(x = "Hotel Name", y = "Frequency",
            title = " Hotels by Figure")
     
     # Stacked Bar Chart
     ggplot(Tolu_project_data, aes(x = Hotel_Name, fill = Booking_status))+
       geom_bar(position = "dodge")+ labs(title = "Booking status by Hotel")
 
ggplot(Tolu_project_data, aes(x = Hotel_Name, fill = meal))+
       geom_bar(position = "dogde")+
       labs(title = "Meal offered by Hotel")
 
 
     ggplot(Tolu_project_data, aes(x = reservation_status, fill = Hotel_Name))+
       geom_bar(position = "dodge")+ labs(title = "Reservation status by Hotel")
     
     
   
     
     ggplot(Tolu_project_data, aes(x = Hotel_Name, fill = market_segment))+
       geom_bar(position = "dodge")+
       labs(title = "Market Segment by Hotel",
            subtitle = "The Market segment report by Hotel Type")
     
     ggplot(Tolu_project_data, aes(x = Booking_status, fill = distribution_channel))+
       geom_bar(position = "dodge")+
       labs(y = "Frequency", title = "Distribution channel by Booking Status",
            subtitle = "Customer booking status by distribution channel")
 
     # MEAN OF LEAD TIME
     Mean_lead_time <- aggregate(lead_time ~ market_segment,
                                 Tolu_project_data, mean)
     
     View(Mean_lead_time)
     
     ggplot(Mean_lead_time, aes(x = market_segment, y = lead_time))+
       geom_bar(stat = "identity", fill = "cornflowerblue")+
       labs(y = "Average number of days",
            title = "Mean Lead time by Market Segment",
            subtitle = "The mean number of days that elapsed between the entering date of the booking into the PMS and the arrival date")
 
     # MEAN OF LEAD TIME by distribution channel
     
     Mean_lead_time <- aggregate(lead_time ~ distribution_channel,
                                 Tolu_project_data, mean)
     
     View(Mean_lead_time)
     
     ggplot(Mean_lead_time, aes(x = distribution_channel, y = lead_time))+
       geom_bar(stat = "identity", fill = "purple")+
       labs(y = "Average number of days",
            title = "Mean Lead time by Distribution Channel",
            subtitle = "The mean number of days that elapsed between the entering date of the booking into the PMS and the arrival date")
 
       ggplot(Tolu_project_data, aes(x = customer_type))+
         geom_col(aes(y = adults, fill = "adults"), position = "stack")+
         geom_col(aes(y = children, fill = "children"), position = "stack")+
         geom_col(aes(y = babies, fill = "babies"), position = "stack")+
         labs(title = "Total number of customers by customer type and categories",
              subtitle = "Chart showing the number of customers that booked the hotels by customer type and categories",
              y = "Frequency")
 
