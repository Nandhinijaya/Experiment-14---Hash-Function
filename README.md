# Experiment-14---Hash-Function
# Aim:
To implement a cryptographic hash function to compute the
hash of a message.

# Algorithm Steps:

1. Define a simple_hash function that sums ASCII values of the
message, applying a multiplier to simulate a hash.
2. Define verify_message to check if the hash of a received
message matches the original hash.
3. Set the plaintext message.
4. Display the plaintext message.
5. Compute and display the hash value of the message.
6. To verify, recompute the hash of the received message and
compare it to the original hash.
7. Print whether verification succeeded or failed.

# Program:
```
#include <stdio.h>
#include <string.h>

unsigned int simple_hash(char *message) {
    unsigned int hash = 0;
    for (int i = 0; i < strlen(message); i++) {
        hash += message[i];
        hash *= 31;
    }
    return hash;
}

int verify_message(char *original, unsigned int hash_value) {
    return simple_hash(original) == hash_value;
}

int main() {
    printf("Experiment 14 - Hash Algorithm\n");

    char message[] = "nandhini";
    unsigned int hash_value = simple_hash(message);

    printf("Plaintext message: %s\n", message);
    printf("Hash value: %u\n", hash_value);

    char received_message[] = "preethi";
    if (verify_message(received_message, hash_value)) {
        printf("Message verified successfully.\n");
    } else {
        printf("Message verification failed.\n");
    }

    return 0;
}

```
# Output:
![image](https://github.com/user-attachments/assets/3b395b3c-716f-4905-81df-837ddf1082da)

# Result:
The hash value of the message is successfully computed using a
simple hash function.
