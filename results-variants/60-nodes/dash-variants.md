## Metric Results - 60 nodes
Here we show graphics relative to CPU, memory and event latency metrics of our pubsub middleware in different scenarios. This results were collected from a testground environment with 60 nodes:
- Executed on: ubuntu VM with 126GB RAM and 16 cores.
- Latency between peers: 10ms

Notes:
- max measures of cpu and memory are used to detect runs that suffered external noise from outside processes.
- the FastDelivery just as a scenario because of its pub-centralized nature.
- correctness metrics are the sum of all runs.
- a miss at FastDelivery means that he failed to find the Advertising board or failure of event receiving, while at ScoutSubs only the latter. Duplicated events means that event has already been received by sub.

### Normal Scenario
4 publishers publishing a event and the rest are suscribing, each one to two predicates.

#### Correctness Analysis
Expected events to be received = 112
Duplicated events relative to total
- Base-Unreliable     = 16.97 %
- Redirect-Unreliable = 11.61 %
- Base-Reliable       = 10.72 %
- Redirect-Reliable   = 9.822 %
- Fast-Delivery       = 0.000 %


```python
import process_run

process_run.plot_everything("normal")
```


    
![png](output_1_0.png)
    



    
![png](output_1_1.png)
    



    
![png](output_1_2.png)
    



    
![png](output_1_3.png)
    



    
![png](output_1_4.png)
    


    



    
![png](output_1_6.png)
    


    


### Subscription Burst Scenario
The first subscription round here is identical to the normal scenario, but at the publishing scenario the subscribers will make new subs as the 3 publishers publish their events. This subs are irrelevant for the event delivery, the objective is to overload the system a bit.

#### Correctness Analysis
Expected events to be received = 112
Duplicated events relative to total
- Base-Unreliable     = 16.97 %
- Redirect-Unreliable = 11.61 %
- Base-Reliable       = 10.72 %
- Redirect-Reliable   = 9.822 %


```python
import process_run

process_run.plot_everything("subBurst")
```


    
![png](output_3_0.png)
    



    
![png](output_3_1.png)
    



    
![png](output_3_2.png)
    



    
![png](output_3_3.png)
    



    
![png](output_3_4.png)
    


    



    
![png](output_3_6.png)
    


    


### Event Burst Scenario
The subscription round here is identical, but this time the same subscribers will publish events. From only 41 subs and 4 pubs (normal scenario) to 41 subs and 41 pubs. Plus the filter tables will have more filters that were added during subscription burst.

#### Correctness Analysis
Expected events to be received = 1323
Duplicated events relative to total
- Base-Unreliable     = 6.954 %
- Redirect-Unreliable = 4.611 %
- Base-Reliable       = 12.33 %
- Redirect-Reliable   = 6.728 %


```python
import process_run

process_run.plot_everything("eventBurst")
```


    
![png](output_5_0.png)
    



    
![png](output_5_1.png)
    



    
![png](output_5_2.png)
    



    
![png](output_5_3.png)
    



    
![png](output_5_4.png)
    


    



    
![png](output_5_6.png)
    


    


### Fault Tolerance Scenario
Here we have a scenario similar to the normal, but this time between the subscription round and the publishing round two nodes fail.

#### Correctness Analysis
Expected events to be received = 108
Duplicated events relative to total
- Base-Unreliable     = 16.67 %
- Redirect-Unreliable = 12.04 %
- Base-Reliable       = 8.334 %
- Redirect-Reliable   = 8.334 %


```python
import process_run

process_run.plot_everything("fault")
```


    
![png](output_7_0.png)
    



    
![png](output_7_1.png)
    



    
![png](output_7_2.png)
    



    
![png](output_7_3.png)
    



    
![png](output_7_4.png)
    


    



    
![png](output_7_6.png)
    


    

