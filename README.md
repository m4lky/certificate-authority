# Certificate Authority (CA)
> This is a repo that can be used to create your own Certificate Authority and sign certificates

### Requirements
 - The only requirement is openssl.  Open your terminal and confirm using command below
```bash
openssl --version
```
### Clone this repository
```bash
git clone https://github.com/m4lky/certificate-authority.git
cd certificate-authority
```

---

## Create the Certificate Authority (CA)
The following steps for creating a CA is a one time operation.

### Generate Private Key for CA
The following command will generate a secure private key for the CA called "ca.key" 

```bash
openssl genrsa -out ca.key 2048
```

###  Configurtaion files 
The Certificate Authority will be using the configuration settings from the files below

 - `ca.conf`

This is used to set the default configuration settings for the Certificate Authority.  You can leave this as default values

 - `req.ca.conf`

Update the section below "my_req_distinguished_name" for your environment.  This will be used when we create the CA certificate associated with the CA

 ```bash
 [ my_req_distinguished_name ]
 C=GB
 ST=Scotland
 L=Edinburgh
 O=m4lky
 OU=HomeCA
 CN=certs.m4lky.com
 ```

### Generate certificate for CA private key
The following command generates a CA certificate `ca.crt` with a validity of 3650 days (10 years)

```bash
openssl req -new -x509 -key ca.key -days 3650 -config req.ca.conf -out ca.crt
```

### Summary of files
You should now have the following files in the current working directory
 - ca.key
 - ca.crt

### Adding the final files and directories for CA
You will need to create a directory for your CA to ouput the certificates it generates
```bash
mkdir newcerts
```

You will also need to generate a file that will be used to track all certificates signed by CA
```bash
touch index.txt
```

Finally, you will need to create a database file for the certificate authority
```bash
echo '01' > serial
```




### 3. Configure environment

```bash
# example
cp .env.example .env
```

---

## 🚀 Steps

### 1. [Step One Title]

Short explanation.

```bash
# command here
```

---

### 2. [Step Two Title]

Short explanation.

```bash
# command here
```

---

### 3. [Step Three Title]

Short explanation.

```bash
# command here
```

---

## ✅ Expected Result

```text
# what success looks like
```

---

## 🧪 Troubleshooting

**Problem:** Describe issue  
**Solution:** How to fix it  

---

## 💡 Notes

- Helpful tip
- Extra info

---

## 🏁 Finished

You should now have:

- ✅ Result 1
- ✅ Result 2
