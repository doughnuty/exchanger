# Price monitoring tool
Learn more about the smallest convertion rates and their sources
## Design overview
- **Exchange rates parser** retrieves the exchange rates from web and publishes the cheapest ones to the corresponding channel. 
- **Broker** removes duplicates from channels and forwards values to the **Subscribers**
- **Subscriber** connects to the **Broker**, requests values from it, and displays them to the end user. 
## Exchange rates parser
Different parse scheme for different API under the same abstraction. Hold up-to-date cheapest prices and update if new found. Separate currency exchange rates so that the way of data management can be easily changed. 
## Broker
Several channels, event driven design. Subscriber doesn't have to specify the exchange source (the cheapest will be shown with the source description). Otherwise, the specified one will be retrieved. 
## Subscriber
Separate formatting from data retrieval. Add acknowledgement tag.
## Usage
## Benefits
- Decoupling, all parts can be hosted separately. 
- Scaling, multiple subscribers are possible to maintain. 
- Fast to retrieve due to the cache in the broker. 
- Easy to add new exchange APIs and update design.
## To-do
## Required libraries