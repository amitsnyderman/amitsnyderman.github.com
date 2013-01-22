---
layout: post
title: "Co-Opting the Genetic Code: DNA Encoding Protocol"
date: 2010-04-26T22:36:23+00:00
categories:
tags:
- school
- itp
---
## Genetic Code

The genetic code is the set of rules by which information encoded in genetic material is translated into proteins by living cells.

Deoxyribonucleic acid (DNA) contains the genetic instructions used in the development and functioning of all known living organisms. The main role of DNA molecules is the **long-term storage of information**.

Units of the genetic code are the nucleotides: adenosine (`A`), cytosine (`C`), guanine (`G`), and thymine (`T`). A triplet of these units are known as a codon, which ultimately represents an amino acid (see [codon to amino acid mapping][codons]). With 4 potential values in three positions, there are 4³ permutations or **64 possible codons** to represent the 20 amino acids.

Just as the letters of the alphabet can be combined to form an almost endless variety of words, amino acids can be linked together in varying sequences to form a vast variety of proteins. Every protein is chemically defined by its unique sequence of amino acid residues, which in turn define the three-dimensional structure of the protein.

## MIME Base 64

Base64 is an encoding scheme that encodes binary data by treating it numerically and translating it into a base 64 representation. For instance, take the following encoding of "Man":

<table>
<tr><th>Text</th><td colspan="8">M</td><td colspan="8">a</td><td colspan="8">n</td></tr>
<tr><th>ASCII</th><td colspan="8">77</td><td colspan="8">97</td><td colspan="8">110</td></tr>
<tr><th>Bit Pattern</th><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td></tr>
<tr><th>Index</th><td colspan="6">19</td><td colspan="6">22</td><td colspan="6">5</td><td colspan="6">46</td></tr>
<tr><th>Base64-Encoded</th><td colspan="6">T</td><td colspan="6">W</td><td colspan="6">F</td><td colspan="6">u</td></tr>
</table>

## Remap

Rather than mapping to a character, I chose to remap the base64 *index* to a codon and thus a protein, resulting in the following table:

<table>
<tr><th>Value</th><th>Character</th><th>Codon</th><th>Amino Acid</th></tr>
<tr><td>0</td><td>A</td><td>AAA</td><td>Lysine (K)</td></tr>
<tr><td>1</td><td>B</td><td>AAC</td><td>Asparagine (N)</td></tr>
<tr><td>2</td><td>C</td><td>AAG</td><td>Lysine (K)</td></tr>
<tr><td>3</td><td>D</td><td>AAT</td><td>Asparagine (N)</td></tr>
<tr><td>4</td><td>E</td><td>ACA</td><td>Threonine (T)</td></tr>
<tr><td>5</td><td>F</td><td>ACC</td><td>Threonine (T)</td></tr>
<tr><td>6</td><td>G</td><td>ACG</td><td>Threonine (T)</td></tr>
<tr><td>7</td><td>H</td><td>ACT</td><td>Threonine (T)</td></tr>
<tr><td>8</td><td>I</td><td>AGA</td><td>Arginine (R)</td></tr>
<tr><td>9</td><td>J</td><td>AGC</td><td>Serine (S)</td></tr>
<tr><td>10</td><td>K</td><td>AGG</td><td>Arginine (R)</td></tr>
<tr><td>11</td><td>L</td><td>AGT</td><td>Serine (S)</td></tr>
<tr><td>12</td><td>M</td><td>ATA</td><td>Isoleucine (I)</td></tr>
<tr><td>13</td><td>N</td><td>ATC</td><td>Isoleucine (I)</td></tr>
<tr><td>14</td><td>O</td><td>ATG</td><td>Methionine (M)</td></tr>
<tr><td>15</td><td>P</td><td>ATT</td><td>Isoleucine (I)</td></tr>
<tr><td>16</td><td>Q</td><td>CAA</td><td>Glutamine (Q)</td></tr>
<tr><td>17</td><td>R</td><td>CAC</td><td>Histidine (H)</td></tr>
<tr><td>18</td><td>S</td><td>CAG</td><td>Glutamine (Q)</td></tr>
<tr><td>19</td><td>T</td><td>CAT</td><td>Histidine (H)</td></tr>
<tr><td>20</td><td>U</td><td>CCA</td><td>Proline (P)</td></tr>
<tr><td>21</td><td>V</td><td>CCC</td><td>Proline (P)</td></tr>
<tr><td>22</td><td>W</td><td>CCG</td><td>Proline (P)</td></tr>
<tr><td>23</td><td>X</td><td>CCT</td><td>Proline (P)</td></tr>
<tr><td>24</td><td>Y</td><td>CGA</td><td>Arginine (R)</td></tr>
<tr><td>25</td><td>Z</td><td>CGC</td><td>Arginine (R)</td></tr>
<tr><td>26</td><td>a</td><td>CGG</td><td>Arginine (R)</td></tr>
<tr><td>27</td><td>b</td><td>CGT</td><td>Arginine (R)</td></tr>
<tr><td>28</td><td>c</td><td>CTA</td><td>Leucine (L)</td></tr>
<tr><td>29</td><td>d</td><td>CTC</td><td>Leucine (L)</td></tr>
<tr><td>30</td><td>e</td><td>CTG</td><td>Leucine (L)</td></tr>
<tr><td>31</td><td>f</td><td>CTT</td><td>Leucine (L)</td></tr>
<tr><td>32</td><td>g</td><td>GAA</td><td>Glutamate (E)</td></tr>
<tr><td>33</td><td>h</td><td>GAC</td><td>Aspartate (D)</td></tr>
<tr><td>34</td><td>i</td><td>GAG</td><td>Glutamate (E)</td></tr>
<tr><td>35</td><td>j</td><td>GAT</td><td>Aspartate (D)</td></tr>
<tr><td>36</td><td>k</td><td>GCA</td><td>Alanine (A)</td></tr>
<tr><td>37</td><td>l</td><td>GCC</td><td>Alanine (A)</td></tr>
<tr><td>38</td><td>m</td><td>GCG</td><td>Alanine (A)</td></tr>
<tr><td>39</td><td>n</td><td>GCT</td><td>Alanine (A)</td></tr>
<tr><td>40</td><td>o</td><td>GGA</td><td>Glycine (G)</td></tr>
<tr><td>41</td><td>p</td><td>GGC</td><td>Glycine (G)</td></tr>
<tr><td>42</td><td>q</td><td>GGG</td><td>Glycine (G)</td></tr>
<tr><td>43</td><td>r</td><td>GGT</td><td>Glycine (G)</td></tr>
<tr><td>44</td><td>s</td><td>GTA</td><td>Valine (V)</td></tr>
<tr><td>45</td><td>t</td><td>GTC</td><td>Valine (V)</td></tr>
<tr><td>46</td><td>u</td><td>GTG</td><td>Valine (V)</td></tr>
<tr><td>47</td><td>v</td><td>GTT</td><td>Valine (V)</td></tr>
<tr><td>48</td><td>w</td><td>TAA</td><td>STOP</td></tr>
<tr><td>49</td><td>x</td><td>TAC</td><td>Tyrosine (Y)</td></tr>
<tr><td>50</td><td>y</td><td>TAG</td><td>STOP</td></tr>
<tr><td>51</td><td>z</td><td>TAT</td><td>Tyrosine (Y)</td></tr>
<tr><td>52</td><td>0</td><td>TCA</td><td>Serine (S)</td></tr>
<tr><td>53</td><td>1</td><td>TCC</td><td>Serine (S)</td></tr>
<tr><td>54</td><td>2</td><td>TCG</td><td>Serine (S)</td></tr>
<tr><td>55</td><td>3</td><td>TCT</td><td>Serine (S)</td></tr>
<tr><td>56</td><td>4</td><td>TGA</td><td>STOP</td></tr>
<tr><td>57</td><td>5</td><td>TGC</td><td>Cystine (C)</td></tr>
<tr><td>58</td><td>6</td><td>TGG</td><td>Tryptophan (W)</td></tr>
<tr><td>59</td><td>7</td><td>TGT</td><td>Cystine (C)</td></tr>
<tr><td>60</td><td>8</td><td>TTA</td><td>Leucine (L)</td></tr>
<tr><td>61</td><td>9</td><td>TTC</td><td>Phenylalanine (F)</td></tr>
<tr><td>62</td><td>+</td><td>TTG</td><td>Leucine (L)</td></tr>
<tr><td>63</td><td>/</td><td>TTT</td><td>Phenylalanine (F)</td></tr>
</table>

This enables you to **encode any binary data as DNA**, including text (Unicode), bitmaps, audio, video, etc. Example, *Hello, world!*:

<table>
<tr><th>Base64</th><td>SGVsbG8sIHdvcmxkIQo=</td></tr>
<tr><th>Base64 Index</th><td>18 6 21 44 27 6 60 44 8 7 29 47 28 38 49 36 8 16 40</td></tr>
<tr><th>DNA</th><td>CAGACGCCCGTACGTACGTTAGTAAGAACTCTCGTTCTAGCGTACGCAAGACAAGGA</td></tr>
<tr><th>Protein</th><td>QTPVRTLVRTLVLAYARQG</td></tr>
</table>

[Try it yourself &raquo;][encode]

## Disk is cheap, who cares?

So why would we want to do this, digital storage is becoming abundant and cheap.

### Non-Digital Library

Via recombinant DNA technologies, one could craft a portable, reproducible, time-resistant library of data. Imagine dormant bacteria, serving as an organic time capsule, waiting to grow and multiply the encoded message. *Bacillus mobydickus* or *Spirilla biblicis*. Perhaps we package into a pill the Britannica protein.

### Spime

> "The key to the Spime is identity. A Spime is, by definition, the protagonist of a documented process. It is an historical entity with an accessible, precise trajectory through space and time." –Bruce Sterling, *Shaping Things*

A spime is an instance of an object, uniquely identified by an ID code. Attached to this ID are a history of manufacture and ownership, geographical position and trails, customization details, public discourse, etc. A spime embodies and communicates its entire being to the external world.

We could **use encoded DNA to embed our own narratives**, family histories and trees, etc. into our own being. *Noncoding DNA* describes sequences that do not encode for protein sequences. Much of this DNA has no known biological function and is sometimes referred to as "junk DNA".

More than 98% of the human genome is non-coding. A human spime could recycle this junk DNA by recombining encoded messages into non-coding DNA regions via in-vitro manipulation or gene therapy techniques. Perhaps it could be used to be of a different encoding? Maybe it already is?

Evolving oral tradition into **hereditary storytelling**.

Below is the presentation given in class:

<div style="width:425px" id="__ss_3948290"><object id="__sse3948290" width="425" height="355"><param name="movie" value="http://static.slidesharecdn.com/swf/ssplayer2.swf?doc=dna-encoding-protocol-100503084421-phpapp01&amp;rel=0&amp;stripped_title=dna-encoding-protocol" /><param name="allowFullScreen" value="true"/><param name="allowScriptAccess" value="always"/><embed name="__sse3948290" src="http://static.slidesharecdn.com/swf/ssplayer2.swf?doc=dna-encoding-protocol-100503084421-phpapp01&amp;rel=0&amp;stripped_title=dna-encoding-protocol" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" width="425" height="355"></embed></object></div>

[codons]: http://upload.wikimedia.org/wikipedia/en/d/d6/GeneticCode21-version-2.svg
[encode]: http://amitsnyderman.com/school/designfrontiers/encoder.php
