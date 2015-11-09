# SE1_Parkhaus

![Alt text](http://g.gravizo.com/g?
  digraph G {
    @startuml

title Parkhaus Class Diagram

interface CarParkInterface {
}

class CarPark implements CarParkInterface {
int carCounter
Map/ArrayList cars

+ payCash()
+ payCard()
+ createTicket()

+ {static} int salesVolume()
+ {static} int meanParkingTime()
+ {static} int freeLots()
}

class CarParkEnterprise extends CarPark {
+ payEnterprise()
}

class Car {
int id
LocalTime enterTime
LocalTIme leaveTime
boolean isEnterpriseCustomer

+ Car(int number)
+ long getSeconds()

+ enterCarPark()
+ leaveCarPark()
diese beiden Methoden
rufen die Req-Handler auf
}


class RequestHandler implements HttpHandler {
+ void handle(HttpExchange he)
}

class EnterRequestHandler implements RequestHandler {
+ void handle(HttpExchange he)
}

class LeaveRequestHandler implements RequestHandler {
+ void handle(HttpExchange he)
}

class HttpCarServer {
- int port = 8182
+ HttpCarServer(int port)

+ void start()
}

class Main {
+ {static} void main(String[] args)
}

@enduml
  }
)
