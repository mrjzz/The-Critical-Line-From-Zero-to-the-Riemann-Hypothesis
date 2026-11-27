# How did they crack the Riemann Hypothesis? | Numberphile, English audio

Brady Haran interviews Oxford mathematician Jon Keating. Numberphile published the episode on 23 November 2026. Tony Padilla appeared in the earlier reaction video heard again over the end card. The Bilibili upload is by 旁白_B. [Numberphile episode](https://www.numberphile.com/videos/how-did-they-crack-the-riemann-hypothesis) · [Original on YouTube](https://www.youtube.com/watch?v=PjGlt3y-Nco) · [Earlier reaction](https://www.numberphile.com/videos/the-riemann-hypothesis-falls)

Edited from the local P2 audio recognition, with names, speaker turns and notation checked against the original episode, its YouTube auto-generated English track and the on-screen mathematics. All 86 segments are included. Repeated fillers are trimmed, and ellipses at adjacent timestamps carry a sentence across the cut. Times use the P2 clock (26:31.52). Each link seeks to the whole second containing the start. The Chinese dub has its own clock (25:40.80). [P2 English audio](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=0) · [P1 Chinese dub](https://www.bilibili.com/video/BV17uydzSEbF/?p=1&t=0) · [中文分段稿与双轨导航](BV17uydzSEbF.md)

## Proof status checked on 27 November 2026

- **Levent Alpöge and Claude.** Alpöge released the Lean formalization on 20 November. On 21 November the Lean FRO and Mathlib Initiative certified the statement and proof of classical RH. Michael “Mike” Rubinstein records checks of five theorems including GRH for Dirichlet $L$-functions. His expository draft for zeta identifies the steps still to be written out in classical terms in §I.12. [Alpöge’s announcement](https://alpo.ge/remark.pdf) · [Joint verification statement](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) · [Rubinstein’s checks and working draft](https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/)
- **Alessandro Maria Masullo.** His manuscript *The Music of the Primes* proposes GRH for unitary Hecke characters over all number fields. He describes an intended further year of revision. Ravi Vakil posted the draft and subsequently reported objections. The independent formalization project’s 26 November update still listed an open step on the main route, cancellation of contributions from zeros outside a strip in the trace formula. [Author’s preface, p. 6](https://math216.wordpress.com/wp-content/uploads/2026/11/the-music-of-the-primes.pdf#page=6) · [Vakil’s update](https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/) · [Formalization project’s open issues](https://github.com/mccorvie/riemann-masullo/issues/7349)

## Listening guide

- [02:38](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=158)　Who gets credit if both arguments work?
- [07:03](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=423)　Follow the half from the real axis into the exponent in the prime-counting error.
- [10:39](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=639)　Why make the weight vanish at the endpoint?
- [13:34](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=814)　Pause on the yellow correction to Chebyshev’s binomial argument.
- [15:13](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=913)　Is there a magic number? Listen for the step involving lattices and theta sums.
- [18:42](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1122)　Switch to Masullo’s proposal and the polynomial analogue of a prime.
- [22:23](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1343)　Which family does the formalized GRH actually cover?
- [25:32](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1532)　The last question. How does it feel to see a lifelong problem fall?

## P2 segment transcript

### Two buses at once

[00:00.00–00:16.84](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=0)　**Keating** I do not understand, and I suspect no human completely understands. But that seems to be its strategy. When I look at that, I am completely in awe and in wonderment. **Haran** Hi, everyone. Before we hear more from Jon Keating, just a little bit more context from me.

[00:16.84–00:39.52](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=16)　**Haran** Last Friday, as we record, it was announced that the Riemann hypothesis had been proven. Proven to be true, by the way. We made a quick reaction video, me and Tony Padilla. I'll put links down below. While we were recording this, it was announced that a human may also have solved the Riemann hypothesis. The proof has been released. It's a little more incomplete, reading between the lines.

[00:39.52–00:55.68](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=39)　**Haran** Today we're going to discuss both the AI proof and the human proof, maybe, and a little about how they work. Let's do it. What do they say? You can wait forever for a bus and then two come along at once.

[00:55.68–01:11.10](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=55)　**Keating** Absolutely. This is the surprise that we face. The big one is the Riemann hypothesis, one of the iconic problems of mathematics. It's fallen to AI. Claude…

[01:11.10–01:32.78](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=71)　**Keating** …has produced a proof, a *purported* proof. It's not yet been checked by humans, but it's very credible that this is a proof. Within a day, a human being, Alessandro Masullo, said he was close to a proof and released a manuscript…

[01:32.78–01:49.20](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=92)　**Keating** …that he says contains the essence of a proof. It's not been checked completely by him yet, or by others. I think he was hoping to spend longer polishing it, but he's released his ideas, and those ideas look very interesting as well. **Haran** Masullo, this Masullo chap…

[01:49.20–02:06.48](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=109)　**Haran** …who you know, I believe? **Keating** I have met him. He's known on the circuit. He was a very brilliant student at Stanford a number of years ago, like a decade ago. People had a very high opinion of him there. It seems he's been spending the last decade…

[02:06.48–02:20.68](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=126)　**Keating** …producing a proof of the Riemann hypothesis. **Haran** And he's had his hand forced to put it out a bit prematurely because of… **Keating** Exactly. I think he would have liked another year to polish what he's done, to check everything, to optimize what he's written.

[02:20.68–02:38.80](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=140)　**Keating** He doesn't have that luxury, so he's produced a rough manuscript. I think he would have wished to spend longer polishing it, but it contains the essence of his ideas. **Haran** If they both end up having a proof, I don't know, you don't know what's going to happen. If they both end up being…

[02:38.80–02:53.04](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=158)　**Haran** …proofs, who's going to get the glory? Will it be Claude by a few hours? Is that how it works? **Keating** I think one of the consequences of AI coming into mathematics and doing…

[02:53.04–03:15.80](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=173)　**Keating** …so many wonderful things in the last month or two is that perhaps we have to give up on the idea of credit. Mathematics is becoming more of a team sport. There may well be collaborations set up between humans with AI, and perhaps we should get away from this idea of credit. If you insist, I think they both deserve the credit…

[03:15.80–03:37.02](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=195)　**Keating** …personally, assuming both proofs stack up. Masullo's proof, I gather, may not be completely correct in every detail. He himself admits he wanted longer to check it. The question is whether the gaps are easily fixable by a professional mathematician. If so, he deserves the credit as well, in my opinion.

[03:37.02–03:57.56](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=217)　**Haran** Before filming, we were talking about gaps in proofs. You said they're not the fatal flaw one might initially think. You can publish a proof that has a gap and it's still considered legit? **Keating** It depends how easy the gap is to fix. If you're building a proof that may take hundreds of pages to write…

[03:57.56–04:19.10](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=237)　**Keating** …you're bound to make a small slip somewhere. Mathematicians understand that. Provided it's easily fixable by a professional mathematician, maybe yourself, people will still give you the credit. If your purported proof contains a huge…

### What Keating learned from Rubinstein

[04:19.10–04:41.54](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=259)　**Keating** …error or gap in the logic that's extremely difficult to fix, and would take a long time and many people, it would be considered incomplete. Credit would be shared by the people who eventually fix it, if they can. **Haran** Can we go back to the Claude proof? Levent and his Claude AI have published.

[04:41.54–04:56.34](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=281)　**Haran** Obviously you haven't read it. No one can read it, probably, certainly in the time frames we're filming on. Can you tell me what you understand of it? What have you gleaned from what you've read and heard? What should we think about this? **Keating** Yeah, so…

[04:56.34–05:14.82](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=296)　**Keating** It's a quarter of a million pages. Absolutely, I've not read that, and no human has. That's the interesting sociological situation we find ourselves in. What I've gleaned through talking to people, through having advice from people who have…

> **Reader’s note.** The quarter-million pages are Keating’s way of conveying the scale. The published material was a Lean development of 175,187 files, about 17 million lines. [Rubinstein’s verification record](https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/)

[05:14.82–05:34.52](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=314)　**Keating** …gone through the Lean proof at some level. In particular, my collaborator and good friend Mike Rubinstein has told me what he's understood from the proof. It uses some very classical ideas but combines really very new thinking about those…

[05:34.52–05:54.66](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=334)　**Keating** …ideas. Riemann wrote down the Riemann hypothesis in the context of understanding the prime numbers. It's important because it tells us about the primes. You can reverse that logic. The primes tell us about the zeros of the Riemann zeta function, which is often how the hypothesis is framed.

[05:54.66–06:13.74](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=354)　**Keating** Usually it's framed as the zeros of the Riemann zeta function lying on a line in the complex plane with real part one half. That's the picture people have in mind. That's equivalent to a statement about the primes, about the error term in the prime number theorem.

[06:13.74–06:28.68](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=373)　**Keating** It seems to be that latter phrasing, in terms of counting primes, that Claude has used. That's most of its analysis as far as I understand it. Everything I say…

[06:28.68–06:48.76](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=388)　**Keating** …is gleaned from conversations and rumours and whispers. From what I understand currently, the basic idea is to analyse sums over prime numbers, and to do it in a way that is in some sense classical. It goes back to ideas of Chebyshev before Riemann, in about 1850.

### From the critical line to prime-counting errors

[06:48.76–07:03.44](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=408)　**Keating** Would you like me to show you what I mean by that, Brady? **Haran** I would love you to. Thank you. **Keating** The hypothesis is that the zeros of the Riemann zeta function lie on a line in the complex plane…

[07:03.44–07:17.74](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=423)　**Keating** …with real part one half. That's the horizontal coordinate of these points. They all lie exactly on this line. **Haran** These are the nontrivial zeros we hear about? **Keating** Exactly so.

[07:17.74–07:38.08](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=437)　**Keating** The fact that they all lie on the line with real part one half tells us something about the distribution of prime numbers. The prime number theorem says that if you count primes whose value is less than or equal to $x$, this should be…

[07:38.08–07:55.66](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=458)　**Keating** …something like the integral $\int_2^x dy/\log y$. That was guessed by Gauss in the late 1790s. Then there's an error term, $R(x)$.

[07:55.66–08:12.96](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=475)　**Keating** It's believed that the size of $R(x)$, the remainder, the error you make in simply sticking to the integral, should be less than or of the order of something like $x$…

[08:12.96–08:27.28](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=492)　**Keating** …to the one half plus a tiny bit, a bit that's as tiny as you can imagine. Epsilon can be as small as you like. Essentially the idea is that the size of this is the square root of $x$.

[08:27.28–08:44.84](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=507)　**Keating** That's equivalent to the Riemann hypothesis. The statement that the zeros lie on the line with real part one half. That half becomes this half [in the exponent]. All the zeros lying on this line is equivalent to this statement here.

[08:44.84–09:06.80](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=524)　**Keating** If there were a zero off the line, say with real part three quarters, this would be $x$ to the power three quarters. There's another way to phrase this which is a little easier. Define a function $\Lambda(n)$, the von Mangoldt function, to be $\log p$ if $n$…

> **Reading the graph.** The zeros at issue are the nontrivial ones. For every fixed $\varepsilon>0$ the bound is $|R(x)|=O_\varepsilon(x^{1/2+\varepsilon})$. A zero with real part $3/4$ would contribute an oscillation on the scale of that exponent.

[09:06.80–09:22.18](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=546)　**Keating** …is a power, any [positive] integer power, of a prime $p$, and zero otherwise. So $\Lambda(2)$ is going to be $\log 2$ because…

[09:22.18–09:41.02](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=562)　**Keating** …two is a prime. $\Lambda(4)$ is $\log 2$ because four is two squared. $\Lambda(6)$ is zero because six isn't a prime or a power of a prime. Another way of saying the Riemann hypothesis is that if I sum…

[09:41.02–10:00.86](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=581)　**Keating** …$\Lambda(n)$ for $n$ up to $x$, this should be $x$ plus an error term which I'll write as little $r(x)$. Again, the statement about little $r(x)$, the Riemann hypothesis…

[10:00.86–10:19.34](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=600)　**Keating** …is that this is of order $x$ to the power a half plus epsilon. So if you want to prove the Riemann hypothesis, you either prove something about the zeros, or you prove something about the primes.

[10:19.34–10:39.94](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=619)　**Keating** Take the sum of $\Lambda(n)$ up to $x$ and subtract $x$. You're left with something roughly of size $x^{1/2}$. Mathematicians don't quite like this formulation. You're summing $\Lambda(n)$ up to $x$ and you're weighting this…

[10:39.94–10:56.12](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=639)　**Keating** …by one up to $x$ and zero otherwise. You're cutting off the sum sharply, which isn't optimal for doing calculus. Another way of saying this is to sum, over $n\le x$, $\Lambda(n)$…

[10:56.12–11:18.28](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=656)　**Keating** …times $(x/n-1)$. This takes the weight down to zero at $x$. The term vanishes at the endpoint, so it's a slightly nicer object to look at. If we take this sum to be…

[11:18.28–11:39.84](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=678)　**Keating** …$x\log x$ minus a constant, one plus Euler's constant, times $x$, plus, what shall I call this, $\rho(x)$, then the Riemann hypothesis is equivalent to the statement that $\rho(x)$ is…

[11:39.84–11:58.52](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=699)　**Keating** …less than or equal to $x^{1/2+\varepsilon}$ for all $x$ large enough. It's in this form that Claude seems to have started. Claude has gone back to an idea that…

> **Reading the board.** $\rho(x)=\sum_{n\le x}\Lambda(n)(x/n-1)-x\log x+(1+\gamma)x$. Here $\gamma$ is Euler’s constant. The inequality Keating writes for this particular smoothed remainder is one-sided. [Alpöge’s outline, p. 3, item 5](https://alpo.ge/remark.pdf#page=3)

### Chebyshev’s binomial coefficient

[11:58.52–12:17.04](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=718)　**Keating** …predates Riemann, which is due to Chebyshev. Chebyshev wanted to understand and prove the prime number theorem, either in this form here, where you count the primes up to $x$, or this form here, where you sum…

[12:17.04–12:31.58](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=737)　**Keating** …the von Mangoldt function up to $x$. He had a beautifully simple idea. Let's take the binomial coefficient…

[12:31.58–12:46.54](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=751)　**Keating** …$2n$ choose $n$. As your viewers will know, Brady, binomial coefficients appear when you expand $(1+x)^{2n}$.

[12:46.54–13:01.48](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=766)　**Keating** Expand that in powers of $x$. This is the middle coefficient in the expansion. It has a remarkable property. It's an integer. It has no prime divisors beyond $2n$.

[13:01.48–13:17.74](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=781)　**Keating** The primes between $n$ and $2n$ appear to the first power. Up to $n$ they can appear with a slightly larger power. This gave Chebyshev a way into understanding the primes, because we know that this [coefficient]…

[13:17.74–13:38.72](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=797)　**Keating** …is less than or equal to $4^n$. That's quite elementary. Chebyshev realized that this binomial expression is greater than or equal to the sum of $\log p$ [see the on-screen correction below]. So he had a way of saying, well, I can understand…

> **On-screen correction.** The yellow arrow supplies the exponential. For primes $n<p\le 2n$, each divides $\binom{2n}{n}$ once. Thus $\exp(\sum\log p)=\prod p\le\binom{2n}{n}\le 4^n$. Taking logs gives $\sum\log p\le n\log 4$. The screen includes $p=n$ at the lower endpoint. The lower endpoint must be open. For instance, 3 does not divide $\binom{6}{3}=20$. [Pause on the correction](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=814)

[13:38.72–13:57.58](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=818)　**Keating** …how to count primes from this formula. This tells me the coefficient is at most $4^n$. If I take logarithms on both sides, I don't get exactly this, but it leads to a statement. The sum of $\Lambda(n)$ over $n\le x$…

[13:57.58–14:17.42](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=837)　**Keating** …is less than or equal to some constant, which I'll call $a$, times $x$. In the prime number theorem you really want to say $a$ is one. Chebyshev couldn't achieve that, but he did achieve the bound with a constant. He came quite close to the prime number theorem.

[14:17.42–14:36.96](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=857)　**Keating** Riemann got us over the line, or at least those who made Riemann's work rigorous got us over the line. Chebyshev got us close. What Claude has done, from my very limited understanding, is take a much better number here than the binomial coefficient.

> **Reader’s note.** The prime number theorem says $\sum_{n\le x}\Lambda(n)/x\to1$. A constant-factor bound is one step towards that limit. Hadamard and de la Vallée Poussin proved the theorem independently in 1896. [Clay’s note on Riemann’s manuscript](https://www.claymath.org/collections/riemanns-1859-manuscript/)

[14:36.96–14:57.22](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=876)　**Keating** It's chosen a way smarter number but it's using the same idea. Choose a number whose size you can bound and whose prime factorization you know something about. That tells us how to bound sums over primes. It can do it with such accuracy…

[14:57.22–15:13.00](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=897)　**Keating** …that in this formula it can achieve the prime number theorem and get a remainder of the right order of magnitude to guarantee the Riemann hypothesis. **Haran** Do you know what the magic number was that it put in [place of] that $2n$?

[15:13.00–15:33.28](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=913)　**Keating** That's where the magic lies and why it takes 250,000 pages. I've dramatically oversimplified. It hasn't chosen one constant. It's chosen a whole array of constants and optimized with respect to them. The way it constructed that number involves…

[15:33.28–15:54.52](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=933)　**Keating** …lattices, theta sums. It's a very complicated game. To be honest, Brady, I do not understand, and I suspect no human completely understands. But that seems to be its strategy. **Haran** I read Levent's remarks. He was watching Claude sparkle or dance. It was this wonderful thing he was seeing happen.

> **Reader’s note.** One specific choice in Alpöge’s own description is a chain of theta lifts of length about $\sqrt{X}$ for a von Mangoldt sum of length $X$. This gives some content to the analogy of “choosing a number.” [Alpöge’s account, p. 1](https://alpo.ge/remark.pdf#page=1)

[15:54.52–16:13.64](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=954)　**Haran** Have you and other mathematicians got any sense of that yet, or are you still scratching your heads? Are people looking at it and going, “Wow, that is wonderful”? **Keating** I have to say that this proof strategy is quite classical. The basic idea goes back to Chebyshev.

[16:13.64–16:30.40](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=973)　**Keating** But there's way more modern mathematics in there to choose a better number whose size we can bound and whose prime distribution we understand. The choice is really magical. When I look at that I am completely…

[16:30.40–16:47.46](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=990)　**Keating** …in awe and in wonderment that you could have made this work. It's a very, very complicated construction. Please don't misunderstand me. There's no simple number I can write down here. There's a whole algorithm that leads to complicated estimates that do the job.

### What can one mathematician understand?

[16:47.46–17:08.72](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1007)　**Keating** To have made that work is really remarkable. **Haran** How do you feel about the fact that it was AI that did it and not one of your fellow humans? **Keating** Masullo is a fellow human, and he may have got there within a few hours. That's essentially the same time in my language. Am I disappointed Claude did it?

[17:08.72–17:31.62](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1028)　**Keating** I might have been earlier in my career when I was trying to do this myself. To be honest, Brady, I just want to understand it. My job is to understand the world of mathematics and the universe of numbers. If Claude helps us along the way, I won't be that disappointed, provided I can understand it at some stage.

[17:31.62–17:46.16](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1051)　**Keating** What I'm hearing suggests it may be within the bounds of possibility that we will understand this. Then we'll have learned a new proof strategy. It'll be remarkable, and I'll be very excited by that.

[17:46.16–18:07.02](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1066)　**Haran** Is it feasible that we're approaching a stage where artificial intelligence starts to make breakthroughs, realizations and proofs beyond your hardware, beyond any human's hardware, and we have to accept we can't understand? **Keating** That is possible. Humans have faced this before.

[18:07.02–18:25.38](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1087)　**Keating** If I want to see the stars, I'd quite like to see them with my own eyes. There are certain things in the universe that the Hubble Space Telescope can see that my eyes can't. I'm prepared to accept that Hubble does a better job than my eyes. I look at the pictures it produces in wonderment…

[18:25.38–18:42.64](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1105)　**Keating** …pictures of nebulae, for instance. Perhaps mathematicians are going to have to come to terms with the fact that the organ we see with, our brain, isn't as powerful as some machines we humans have built. Perhaps we've just got to trust those machines.

### Masullo and the polynomial analogy

[18:42.64–19:03.58](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1122)　**Haran** Can you give me any feeling for what Masullo did? He didn't use the technique you just explained? **Keating** No, a completely different technique. I've not been through Masullo's paper. I've scanned it, but it's a very dense read, many hundreds of pages long.

[19:03.58–19:19.88](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1143)　**Keating** Even though it's written by a human, it's going to take humans a long time to go through. His strategy is rather different, based more on one that came out of twentieth-century mathematics. There are…

[19:19.88–19:35.80](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1159)　**Keating** …functions similar to the Riemann zeta function. The zeta function is constructed from prime numbers, or sums over integers. There are analogues constructed by summing over polynomials…

[19:35.80–19:57.54](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1175)　**Keating** …where the primes are replaced by irreducible polynomials, ones you can't factorize. You do arithmetic modulo some prime $q$, let's say. You can add polynomials modulo $q$, multiply them and factorize them. You can construct a whole world very similar to…

[19:57.54–20:19.48](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1197)　**Keating** …the number theory we know and love. In that world you can construct something like the Riemann hypothesis. It was proved in the twentieth century. The analogues of zeta are simpler in that case because they have only finitely many zeros. That makes the job easier, although it's still an incredibly impressive achievement. André Weil…

[20:19.48–20:37.10](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1219)　**Keating** …Grothendieck, Pierre Deligne… Many people contributed to a proof that developed through the twentieth century. Masullo seems to have gone back to that. Other people have had this idea. My very good friend Alain Connes has been taking that approach.

[20:37.10–20:52.70](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1237)　**Keating** Paul Cohen, a very great mathematician at Stanford, explored it for many years. It seems Masullo has built on the idea and found a way to take ideas that work for polynomials and make them work for integers and ordinary primes.

### The cousins of zeta

[20:52.70–21:13.02](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1252)　**Keating** What Claude has done with Levent Alpöge is to prove the generalized Riemann hypothesis, which is way more powerful, and actually even more exciting, than the Riemann hypothesis. Zeta has various cousins. We made a film about these some years ago…

[21:13.02–21:28.16](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1273)　**Keating** …Brady, where I describe these in some detail. Viewers who want to understand this might go back to that film. The cousins all look like the Riemann zeta function in that they have…

[21:28.16–21:43.30](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1288)　**Keating** …a Dirichlet series. You can write them as sums over the positive integers. They have an Euler product, so you can relate them to the primes. Like zeta, they sit in the complex plane.

[21:43.30–22:02.46](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1303)　**Keating** There's the Riemann zeta function. Here are two other $L$-functions. **Haran** So $L$-functions are these cousins? **Keating** These are the cousins. They all have a Riemann hypothesis. If you normalize them correctly, their zeros should be on the line with real part one half. Their zeros differ from zeta's zeros.

[22:02.46–22:23.78](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1322)　**Keating** They're different functions, but in some sense they look the same. **Haran** Just where the little speckles are on the line, they're in different places? **Keating** Exactly. Their construction is very similar. They involve primes and sums over integers, but you construct those sums a bit differently. There's a vastly…

[22:23.78–22:45.18](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1343)　**Keating** …general theory of where these $L$-functions come from. They're related to very interesting symmetries in mathematics, to representation theory. That's the Langlands programme. This whole array of $L$-functions, Claude and Levent are claiming a proof for all of them. [See the scope note below.]

> **Scope note.** The verified family here consists of **all Dirichlet $L$-functions**, including zeta as a special case. Keating’s account of representation theory describes a much wider family. Masullo’s proposed Hecke result has its own status, given above. [Five verified theorem statements and their interpretation](https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/)

[22:45.18–23:05.54](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1365)　**Keating** That's tremendously important. The more $L$-functions you have, the more information they give you about primes and about numbers in general. Zeta already tells us quite a lot, including the error term in the prime number theorem. If you know the Riemann hypothesis for all these $L$-functions…

[23:05.54–23:22.74](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1385)　**Keating** …every one gives you more information about the primes. We're stacking up information. If it's true for all of them, it gives us incredibly detailed information about prime numbers, for example the kind of information used in cryptography.

[23:22.74–23:40.90](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1402)　**Keating** It has a lot of implications there. That's a story for another day, Brady, but it's an interesting one. **Haran** If Claude stands up, we've got the Riemann hypothesis as a special case. We've got all the $L$-functions in this big family, which is an even bigger deal.

[23:40.90–24:02.02](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1420)　**Haran** But I read about something called the extended Riemann hypothesis. **Keating** There are other objects that we believe look like $L$-functions too, but don't quite fit the pattern of how we normally set them out. They're outside what I'd call the normal class of $L$-functions. That's a different story.

[24:02.02–24:17.52](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1442)　**Haran** And we haven't got that one? **Keating** We've not got that one, I believe, as far as I understand. **Haran** What's the new Riemann hypothesis? For years I've been saying, “Imagine solving the Riemann hypothesis.” What's the new top of the pile? We're seeing these things fall like tenpins.

### The next problem and a final question

[24:17.52–24:38.10](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1457)　**Haran** What's left? What's the new holy grail? **Keating** Well… **Haran** Collatz? A lot of people are talking about Collatz. **Keating** Collatz is cute. It's a cute problem. I don't know many mathematicians who would see it as having wider implications. One that perhaps has wider implications is the Birch and Swinnerton-Dyer conjecture.

[24:38.10–24:56.58](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1478)　**Haran** Another Millennium Prize Problem. **Keating** Another Millennium Prize Problem that also concerns $L$-functions. They're part of the class I've been talking about. In this case the $L$-functions relate to elliptic curves. The statement of the…

[24:56.58–25:10.68](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1496)　**Keating** …Birch and Swinnerton-Dyer conjecture is that those $L$-functions have a zero right at the centre of the critical strip, where the line on which all the zeros lie meets the real axis…

[25:10.68–25:32.28](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1510)　**Keating** …and that zero contains really interesting information about how many rational points lie on the elliptic curve related to the $L$-function. That would be another huge breakthrough. I have no doubt AI companies have it in their sights, but I've not heard any rumours they've done it yet.

> **Reader’s note.** The Birch and Swinnerton-Dyer conjecture predicts that the order of vanishing of $L(E,s)$ at the centre equals the rank of the group of rational points on an elliptic curve $E/\mathbb Q$. Rank zero predicts a nonzero central value. In the usual arithmetic normalization the centre is $s=1$. [Clay’s BSD problem description](https://www.claymath.org/millennium/birch-and-swinnerton-dyer-conjecture/)

[25:32.28–25:51.36](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1532)　**Haran** It'll probably topple ten minutes before we publish this video. **Keating** Probably. **Haran** Be honest. Was the first emotion a tickle of excitement or a pang of sadness that something was gone from the landscape, a lighthouse had fallen? **Keating** Completely honestly, Brady, it was pure excitement.

[25:51.36–26:13.44](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1551)　**Keating** Of course we would all like to have got there first. But overriding that, I'd just like to understand it. I'm much more interested in that. I want to know how it did it, see how the ideas work, and see whether I can use them in other things I'm very interested in myself.

[26:13.44–26:31.52](https://www.bilibili.com/video/BV17uydzSEbF/?p=2&t=1573)　**End card · earlier reaction video** “I think he will go down in history as somebody who's just cracking math…” “Used this new tool in a way that others just haven't caught up with yet. It's remarkable. It's always his name attached to these things.” “I'll read something he wrote, Tony.” [The clip cuts here.]
