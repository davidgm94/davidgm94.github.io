---
title: "How to start writing an operating system in Zig"
date: 2023-08-07T11:17:37-06:00
draft: false
---

Nowadays when you are a curious programmer and you want to dig into how an operating system works by creating one, there is more possibilities than there used to be some years ago. Do not get me wrong, this is a nice thing to have, but it also introduces some bias, because resources in the Internet that offer some help with introducing new programmers to this corner of the world often tend to obviate the new and all they have to offer is the kirks of 20-30-year-ancient programming models.

# Is Zig a good language to write your operating system on?

TODO

# What architecture should you target (first)?

This depends on what you want and your previous knowledge. If you are into embedded systems, you might want to target a board because you encounter it funny or it will suit your needs. If you are this kind of person, chances are that you are a sufficiently experienced programmer, so this article might not be for you. Anyway, if you are a relatively new programmer or at least you do not have experience in the low-level side of programming, I would surely not recommend that you follow down this path.

Instead, I recommend you to target your developer platform architecture, that is, the CPU you are using right now on your desktop computer. This is because:
- You can test on real hardware without any extra device or accessory
- You can virtualize your OS using your processor and operating system facilities
- In the end, you will have a better feel of how things work and you will not have a distant idea about how an operating system works on real hardware

Most likely, unless you are on an modern Apple device or some geeky aarch64 motherboard/laptop, you will have a x86_64 CPU. This has been the main architecture for desktop systems for a while since the last 32-bit x86 CPU for mainstream machines was produced in the middle 2000s. And since it is the most common architecture, it is also the most documented one. Intel manuals, though rough, are great.

Nevertheless, you are likely to encounter all sorts of legacy documentation relying on 32-bit CPUs, the multiboot protocol and its best friend, GRUB. All these oldies are, at the same time, friends with QEMU, the most common system emulator used by kernel developers. This means QEMU makes it easy for you to develop on all these old protocols and hardware. And one might think: "Well, since the x86_64 architecture is developed later, then it should be harder; I should learn 32-bit first". No, that is absolutely wrong. There is no truth in those words. 32-bit is not a nice platform to develop your own OS. x86_64 is better because the memory model is so much nicer (segmentation is gone for the most part) and the interrupt descriptor table is made simpler, among other reasons that you could mention.

So, whatever you read or hear online, do not listen to this evil gospel. 32-bit is unnecessary sweat, blood and tears today and you should avoid it unless you are specifically targetting real hardware; you should move further and take advantage of every little advancement in software development that is offered to us (as opposed to the countless major flaws of programmers' products that we see everyday).

# What bootloader should you use? Should you write your own bootloader?

TODO
