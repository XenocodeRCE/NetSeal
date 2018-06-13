# Welcome to NetSeal !

Hi! This repo is a revamp of **NetSeal**, a well-known licensing system developped by Aeonhack. It is made to cover license-management on your software, providing extra security features. If you want to learn about NetSeal, you can read me. If you want to play with NetSeal, you can look at the public exemples. If you need help, please open an Issue. If you want to contact us, please do at **support [at] netseal [dot] xyz**.

# Features

Our features are meant to be as simple as possible to use and as safe as possible for your application. We implemented some **Native Protection** on the new NetSeal native Core, **Anti debugging** techniques, **Remote Code Execution** on specific method of your assembly, **Unlimited Server Variables** for you to be able to maximize application dependency over the server, and so much more ... With [NetSeal](https://netseal.xyz/), you have full control over your program.

> Here is a non-exhaustive list of all currently implemented features. 
> This list is a comparative list between old and new **NetSeal**


|                |OLD NETSEAL                          |NEW NETSEAL                         |
|----------------|-------------------------------|-----------------------------|
|Native Core Project                |`[✕]`           |`[✓]`          |
|Unlimited Server Variable          |`[✕]`           |`[✓]`            |
|Online status (shows who is online)          |`[✓]`           |`[✓]`            |
|License banning          |`[✓]`           |`[✓]`            |
|Detailed logs (limited computer informations, connection count, and IP logs)          |`[✓]`           |`[✓]`            |
|License code details (code, created and claim dates, owner, payment tracking)          |`[✓]`           |`[✓]`            |
|Timed or unlimited client session          |`[✕]`           |`[✓]`            |
|Tracking information (such as PayPal email or transaction ID) |`[✓]`           |`[✓]`            |
|Automatic updates                |`[✓]`           |`[✓]`            |
|Machine locking               |`[✓]`           |`[✓]`            |
|Compressed updates (less stress on host and faster for users)                |`[✓]`           |`[✓]`            |
|Exception logging (find errors in your program)                |`[✓]`           |`[✓]`            |
|Choose to receive exceptions directly to your mail                |`[✕]`           |`[✓]`            |
|Native anti reverse engineering and anti sniffing techniques                |`[✕]`           |`[✓]`            |
|Alert mode to remove your application file on every customer's computer                |`[✕]`           |`[✓]`            |
|Native loader to scan computer for cracking tools and potential threats                |`[✕]`           |`[✓]`            |
|In-built anti tamperring techniques                 |`[✕]`           |`[✓]`            |
|Advanced HWID system to bind files to your customer's computer                |`[✕]`           |`[✓]`            |
|Remote code execution of specific method from your file in the cloud                |`[✕]`           |`[✓]`            |
|Server-sided update loader to keep your files always up to date automatically                |`[✓]`           |`[✓]`            |
|Reoccurring server check-in (user stays authenticated and has the latest data)                |`[✓]`           |`[✓]`            |
|Frequent database backups                |`[✓]`           |`[✓]`            |

# Code Implementation

Even if the new NetSeal includes an **Automatic Installer** inside its [Official Admin Dashboard](), you are free to hard-code the implementation. It is as simple as possible, really : we kept the same class-only structure the old netseal had. Note that if you use a VB.NET Project you will need to add a reference to **System.Management** and **System.Security**. If you don't know how to do that, head over our [Wiki]() page to read tutorials !


> Before starting to implement, **you must download the adequate class (.CS / .VB)** and add it to your project.

## C#(Csharp)

> To get a **program ID** please first create a program using the [Official Admin Dashboard]().


```csharp
//program.cs
using System;
using System.Windows.Forms;

namespace YourProgram
{
    static class Program
    {
        // Declare a public static NetSeal instance
        public static NetSeal ns;

        /// <summary>
        /// The main entry point for the application.
        /// </summary>
        [STAThread]
        static void Main(string[] args)
        {
            Application.EnableVisualStyles();
            Application.SetCompatibleTextRenderingDefault(false);

            // Initialize your NetSeal instance with your program ID
            ns = new NetSeal("put your program Id here");

            Application.Run(new Form1());
        }
    }
}

```

## VB(vb.net)

> To get a **program ID** please first create a program using the [Official Admin Dashboard]().


```vb

Public Class Form1

    Public ns As NetSeal

    Public sub New()

        ns = New NetSeal("put your program Id here")
        ' This call is required by the designer.
        InitializeComponent()

        ' Add any initialization after the InitializeComponent() call.

    End Sub
End Class

```
