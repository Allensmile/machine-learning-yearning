## Chapter 42、Addressing data mismatch

**处理数据不匹配**

假设你开发了一个语音识别系统，在训练集和训练测试集上表现的非常好。然而，在开发集上表现糟糕：你有数据不匹配问题。你能怎么做？

我推荐你：(i)试图去理解训练集分布和开发集分布之间数据的什么特性不同。(ii)试图寻找更多算法有问题的和开发集样例更匹配的训练数据【1】。

例如，假设你在语音识别开发集上执行错误分析：你手动检查100个样例，并试图去理解算法在哪里犯错了。你发现系统表现糟糕是因为大部分开发集里的音频剪辑是在车内获取的，而大部分的训练样例是在安静的背景下记录的。发动机和路上的噪音极大地恶化了语音系统的表现。在这种情况下，你可以尝试去获取更多的训练数据，包括在车内的音频剪辑。错误分析的目的是去理解导致数据不匹配的训练集合开发集之间的显著不同。

如果你的训练和训练开发集包含车内录制的音频，你还应该再次确认系统在该数据子集上的表现。如果它在训练集中的车数据上表现良好，但在训练开发集的车数据上表现不佳，那么这进一步验证了获取更多车数据会有帮助的假设。这就是为什么我们讨论的在训练集中包含一些和前一章中开发/测试集来自相同分布的数据的可能性。这样做允许你比较在训练集车数据和开发/测试集车数据上的表现。

不幸的是，这个过程中没有保证。例如，如果你没有获取更多和开发集数据更匹配的训练数据的方法，你可能没有一个清晰的途径来提升性能。

————————

【1】还有一些关于“域适应”的研究——如何在一个分布上训练算法，并将其泛化到一个不同的分布。这些方法通常只适用于特殊类型的问题，并比本章描述的想法使用的少得多。





