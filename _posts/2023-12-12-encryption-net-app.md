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

New addition coming to my code repository. An Encrypter/Decrypter .NET App
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

Check out the [Encryption project][encryption-repo] source code repo on Github.
[encryption-repo]: https://github.com/mariogamedev/EncryptionProtocols