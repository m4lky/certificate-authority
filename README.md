# Certificate Authority (CA)
> This is a repo that can be used to create your own Certificate Authority and sign certificates using PKI

---

## Requirements
 - The only requirement is openssl.  Open your terminal and confirm using command below
```bash
openssl --version
```

---

## Setup

### Clone this repository

```bash
git clone https://github.com/m4lky/certificate-authority.git
cd certificate-authority
```

### 1 . Crete your Certificate Authority (CA)

# Generate Private Key for CA
The following command will generate a secure key called "ca.key"

```bash
openssl genrsa -out ca.key 2048
```

#  Edit Configurtaion file 
The Certificate Authority will be using the configuration settings from the files below

 # ca.conf
 Used to set the default configuration of the Certificate Authority.  You can leave this as default values

 # req.ca.conf
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

# Generate certificate for CA private key

The following command generates a CA certificate 

```bash
openssl req -new -x509 -key ca.key -days 3650 -config req.ca.conf -out ca.crt
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
