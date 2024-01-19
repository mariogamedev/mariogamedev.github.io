---
title: "Encryption .NET App"
date: 2023-12-12T19:22:00-00:00
categories:
  - Code
tags:
  - C#
  - .NET
  - Security
---

**C# Code Showcase: Encryption Protocols Application**

Check out my exhibit showcasing C# code for encrypting and decrypting sensitive data, to ward off unwanted intruders. This application is a practical example of easily extendable code. Explore the simplicity of C# in supporting cybersecurity features through clean coding principles.

Explore a brief code snippet that provides a glimpse into the solution's implementation:

```c#
public class Decrypter
{
    private IFormatter _formatter;
    private IProtocol _protocol;

    public Decrypter(IProtocol protocol, IFormatter formatter)
    {
        _protocol = protocol;
        _formatter = formatter;
    }

    public void Decrypt(string encryptedData)
    {
        byte[] formattedEncryption = Convert.FromHexString(_formatter.Format(encryptedData));
        string decryptedMessage = _protocol.Decrypt(formattedEncryption);
        Console.WriteLine(decryptedMessage);
    }
}
```

**Info Notice:** Current supported protocols are: [Ciphersaber](#).
{: .notice--info}

Check out the [Encryption project][jekyll-gh] source code repo on Github.

[jekyll-gh]: https://github.com/mariogamedev/EncryptionProtocols
