# WARNING DO NOT USE THIS SCRIPT ON ANY NETWORK YOU DO NOT OWN. THE PURPOSE OF THIS SCRIPT IS STRICTLY FOR SIMULATION AGAINST NETWORKS AND SERVERS YOU OWN.

# TOR Traffic Routing Script with Adaptive Machine Learning

This Python script routes traffic through the **Tor network** using **Tor's SOCKS5 proxy**. It ensures anonymity by making all requests through the Tor service, while also employing a machine learning model to adapt based on traffic patterns.

## Key Features

1. **Tor Integration**:
   - Routes all traffic through **Tor's SOCKS5 proxy**, typically located at `localhost:9050`.
   - Uses the `PySocks` library to transparently send all traffic through Tor.
   - Leverages the `requests` library for HTTP requests with proxy settings.

2. **Threading**:
   - Utilizes **multi-threading** to spawn multiple worker threads (default: `MAX_THREADS = 8`), allowing concurrent handling of requests.

3. **SSL Handling**:
   - Establishes SSL-wrapped connections for secure communication between your machine and the target server.

4. **Machine Learning**:
   - Implements an adaptive learning model using **TensorFlow**. The model learns from real-time traffic data and adjusts its predictions dynamically.

5. **Logging**:
   - Logs traffic patterns, including detection of rate limiting, stored in `labels.txt`.

## Requirements

To run this script, you need the following Python packages:

```bash
pip install tensorflow pysocks requests
```

Additionally, ensure that the **Tor service** is installed and running on your system:

```bash
sudo apt install tor
sudo service tor start
```

## Installation

1. Clone this repository or download the script file.

2. Ensure you have Python 3 and the required libraries installed.

3. Start the Tor service as shown above.

## Usage

Run the script from the command line with the target IP and port as arguments:

```bash
python tor_ai_script.py <target_ip> <target_port>
```

### Example

To route traffic to a target IP (e.g., another internal IP) on port 80, use the following command:

```bash
python tor_ai_script.py 127.0.0.1 80
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any enhancements or bug fixes.

## Contact

For any inquiries, please reach out via email at [alexis.gl.lecerc@proton.me](mailto:alexis.gl.lecerc@proton.me).
