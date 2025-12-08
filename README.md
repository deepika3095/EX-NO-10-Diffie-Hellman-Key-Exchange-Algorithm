# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

**NAME : DEEPIKA R**

**REGISTER NO : 212223230038**

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```
#include <stdio.h>

long long power(long long base, long long exp, long long mod)
{
    long long result = 1;
    base = base % mod;

    while (exp > 0)
    {
        result = (result * base) % mod;
        exp--;
    }
    return result;
}

int main()
{
    long long P, G;
    long long a, b;     // private keys
    long long x, y;     // public keys
    long long ka, kb;   // shared secret keys

    printf("\n*** Diffie-Hellman Key Exchange ***\n\n");

    printf("Enter value of P: ");
    scanf("%lld", &P);

    printf("Enter value of G: ");
    scanf("%lld", &G);

    a = 4;
    b = 3;

    printf("\nPrivate key of Alice (a): %lld\n", a);
    printf("Private key of Bob   (b): %lld\n\n", b);

    x = power(G, a, P);    
    y = power(G, b, P);

    ka = power(y, a, P);   
    kb = power(x, b, P);   

    printf("Secret key computed by Alice: %lld\n", ka);
    printf("Secret key computed by Bob  : %lld\n", kb);

    return 0;
}

```


## Output:

<img width="1746" height="677" alt="image" src="https://github.com/user-attachments/assets/c2efe133-944a-4dc7-b9d4-d919cc6dabf8" />


## Result:
  The program is executed successfully

