# Logstash-Kafka Encryption and Authentication Demo

This project demonstrates a basic Docker Compose setup for running Logstash and Kafka with SASL/SCRAM authentication and data encryption using the cipher filter in Logstash.

## Prerequisites

- Docker
- Docker Compose

## Components

- **Zookeeper**: Manages Kafka cluster metadata and maintains the cluster configuration.
- **Kafka**: Handles real-time data feeds with SASL/SCRAM authentication enabled for security.
- **Logstash**: Processes logs, encrypts data fields, and sends encrypted data to Kafka.

## Setup and Configuration

### Kafka and Zookeeper

Kafka is configured with SASL/SCRAM for authentication. The necessary configurations are embedded into the Docker Compose and Kafka configuration files.

### Logstash

Logstash is set up to encrypt the `message` field before sending it to Kafka. The encryption is performed using the AES-256-CBC algorithm.

## Quickstart

To run the project:

1. Clone this repository.
2. Navigate to the repository directory.
3. Execute the following command:

   ```bash
   docker-compose up
   ```

4. To input data into Logstash, use the stdin input by typing into your terminal where Docker Compose is running.

## Configuration Details

### Kafka Configuration

- `config/kafka_server_jaas.conf`: Contains the JAAS configuration for Kafka with a username and password.

### Logstash Configuration

- `logstash/config/logstash.yml`: Basic Logstash configuration.
- `logstash/pipeline/logstash.conf`: Contains the Logstash pipeline configuration for processing and encrypting data.
- `logstash/config/logstash_jaas.conf`: Contains the JAAS configuration for Logstash.

## Encrypting Data

The `cipher` filter in the Logstash configuration is used to encrypt data. The key and initialization vector are currently hardcoded for demonstration purposes but should be securely managed in a production environment.

## Security Considerations

Ensure to replace hardcoded credentials and keys with secure management solutions in a production environment. Consider enabling SSL/TLS for Kafka communication to secure data in transit.

## Contribiuting

Contributions to the project are welcome. Please ensure to follow the existing coding and commit message conventions when making pull requests.

## License

Specify the license under which your project is made available.

## Contact

Provide contact information for the project maintainer or team.


### Notes

1. **Security Warnings**: It's important to highlight in the README that hardcoded values for sensitive data (like encryption keys) are for demonstration purposes only and should be securely managed in a real environment.
2. **Contributions and Issues**: Encourage users to contribute or report issues through GitHub's issue tracker and pull request system.
3. **License**: Don't forget to include a license file or specify the license type in your README, as it informs users how they can legally use the project.
4. **Contact Information**: Adding contact information helps users know how to reach out for more assistance or collaboration.

This README format offers a comprehensive guide to help anyone get started with your project quickly and understand its components and configurations.
