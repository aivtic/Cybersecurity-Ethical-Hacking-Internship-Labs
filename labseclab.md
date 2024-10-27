

### **Lab 2: Implementing Encryption Techniques (Linux Version)**

### **Objective:**
To apply encryption techniques to protect sensitive data at rest and in transit.

### **Duration:**
1.0 hours

### **Materials Needed:**
- A sample dataset (e.g., text file)
- Linux terminal with OpenSSL and Python installed

---

### **Instructions:**

---

### **1. Encryption at Rest**

1. **Setup the Sample Dataset:**
   - Create a sample text file for encryption:
     ```bash
     echo "This is a sample dataset for encryption" > data.txt
     ```

2. **Symmetric Encryption using AES with OpenSSL:**
   - Encrypt the file `data.txt` using AES-256 encryption with OpenSSL:
     ```bash
     openssl enc -aes-256-cbc -salt -in data.txt -out data.txt.enc
     ```
   - When prompted, enter a passphrase to secure the encryption process.

3. **Decrypting the Encrypted File:**
   - To decrypt `data.txt.enc` back to its original form:
     ```bash
     openssl enc -aes-256-cbc -d -in data.txt.enc -out data_decrypted.txt
     ```
   - Enter the same passphrase used during encryption.

4. **Verify Encryption and Decryption:**
   - Compare `data.txt` and `data_decrypted.txt` to ensure successful encryption and decryption:
     ```bash
     diff data.txt data_decrypted.txt
     ```
   - If there’s no output, it means the files are identical.

---

### **2. Encryption in Transit**

1. **Overview of Encryption in Transit:**
   - Data transmitted over networks can be intercepted. Encrypting it in transit secures the data between the client and server.

2. **Setting Up a Simple HTTPS Server Using Python and OpenSSL:**

   - **Generate SSL Certificate and Key Files:**
     - Navigate to your project directory:
       ```bash
       cd ~/server
       ```
     - Generate a self-signed SSL certificate and key:
       ```bash
       openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes
       ```
       - Follow the prompts to create the certificate details.

   - **Create an HTTPS Server Script:**
     - Create a new Python script called `https_server.py`:
       ```bash
       nano https_server.py
       ```
     - Copy and paste the following code into `https_server.py`:

       ```python
       import http.server
       import ssl

       server_address = ('127.0.0.1', 4443)
       httpd = http.server.HTTPServer(server_address, http.server.SimpleHTTPRequestHandler)
       httpd.socket = ssl.wrap_socket(httpd.socket, certfile="cert.pem", keyfile="key.pem", server_side=True)

       print("Serving on https://127.0.0.1:4443")
       httpd.serve_forever()
       ```

   - **Run the HTTPS Server:**
     - In your terminal, run the server:
       ```bash
       python3 https_server.py
       ```

3. **Access the Server via HTTPS:**
   - Open a browser and go to `https://127.0.0.1:4443`.
   - Accept the security warning (due to the self-signed certificate) to proceed.

---

### **Wrap-Up**

- **Review Key Concepts:**
  - Summarize the encryption techniques used:
    - Symmetric encryption with AES for data at rest.
    - Setting up an HTTPS server for encryption in transit.

