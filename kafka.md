Start    

    sudo systemctl start zookeeper.service
    
    sudo systemctl start kafka.service

    sudo systemctl status kafka zookeeper.service

    sudo systemctl status kafka kafka.service

option: create topic 

    sudo /opt/kafka/bin/kafka-topics.sh --bootstrap-server localhost:9092 --create --topic eventNotifier

check topic

    sudo /opt/kafka/bin/kafka-topics.sh describe --topic eventNotifier --bootstrap-server localhost:9092

option: test producing 

    sudo /opt/kafka/bin/kafka-console-producer.sh --topic eventNotifier --bootstrap-server localhost:9092

option test consumer 

    sudo /opt/kafka/bin/kafka-console-consumer.sh --topic eventNotifier --from-begining --bootstrap-server localhost:9092
 
create log directory

    sudo mkdir /tmp/kafka-logs

Set user for log directory

    sudo chown -R kafka:kafka /tmp/kafka-logs
