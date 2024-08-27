---
layout: post
title: Data Reuse Showcase
author: CatalystNeuro team
---

# Unraveling Anesthesia's Effect on Brain Activity
_Data Reuse Highlight: This blog entry is part of an ongoing series that showcases examples of data reuse and reanalysis using publicly available data on DANDI._

Have you ever wondered what happens to your brain when you're under anesthesia? What neural changes coincide with that dramatic loss of consciousness?
In this post, we'll explore how two different research teams investigated this fascinating question using the same data from DANDI Archive's [Dandiset #000458](https://dandiarchive.org/dandiset/000458).

## The Original Study: Peering into the Anesthetized Brain
In June 2023, Dr. Leslie Claar and colleagues from the Allen Institute published their groundbreaking findings in the journal _eLife_ in the article, [“Cortico-thalamo-cortical interactions modulate electrically evoked EEG responses in mice”](https://doi.org/10.7554/eLife.84630.3).
Their approach was comprehensive: they stimulated mouse cortex while simultaneously recording with [electroencephelography](https://doi.org/10.1016/B978-141603618-0.10024-4) (EEG) and [neuropixels probes](https://www.neuropixels.org/), comparing brain activity during wakefulness and under isoflurane anesthesia.

In awake mice, Claar's team observed a robust [event-related potential](https://doi.org/10.4103/0972-6748.57865) (ERP) when they delivered pulsatile electrical stimulation to deep layers of the [motor cortex](https://doi.org/10.1016/B0-08-043076-7/03460-4).
This ERP coincided with a distinct pattern of neural spiking, both locally in the motor cortex and in distant sensorimotor-related [thalamic nuclei](https://www.ncbi.nlm.nih.gov/books/NBK549908). The response followed a three-act play: initial excitation within 25 milliseconds, a period of quiescence for about 125 milliseconds, and finally, a strong rebound excitation before returning to baseline.
When the mice were under anesthesia, the story changed dramatically.
The ERP's amplitude and complexity plummeted in response to the same stimulation.
While the initial excitation persisted in the motor cortex, it vanished in the thalamic nuclei.
The rebound excitation, along with its corresponding ERP component at around 180 milliseconds, was significantly weakened.

Based on these observations, Claar and colleagues proposed that interactions between the cortex and thalamus are responsible for the rebound excitation phase of the stimulus response.
This rebound excitation, in turn, drives the second component of the ERP – a crucial signal of wakefulness.

After their experiments, Claar and her team published their data on DANDI, ensuring that it would remain publicly accessible for any future researchers who wanted to use it. The dataset and manuscript were prepared and published concurrently, which ensured that the dataset included all the paper-relevant data and metadata and curious reviewers could inspect the data directly if they so wished.

## A New Perspective: Zooming in on Synaptic Potentials
Just a few months later, in November 2023, Drs. Richard Burman, Paul Brodersen and colleagues at the University of Oxford wrote a paper that included reanalysis of this data.
Their findings were published in the journal _Neuron_ with the article, [“Active cortical networks promote shunting fast synaptic inhibition _in vivo_”](https://doi.org/10.1016/j.neuron.2023.08.005).
They also investigated the effects of anesthesia on brain activity, but narrowed their focus to the differential function of a specific receptor subtype: [GABA<sub>A</sub>R](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2648504/).

Burman and Brodersen's team used a technique called [_in vivo_ gramicidin perforated patch-clamp recording](10.1254/fpj.113.339), combined with [optogenetic](10.1097/ICU.0000000000000140) activation of GABAergic synaptic inputs.
They compared the GABA<sub>A</sub> receptor equilibrium potential (E<sub>GABA<sub>A</sub>R</sub>) in mice during wakefulness and under urethane anesthesia.

Their findings were striking. In anesthetized mice, GABA<sub>A</sub> receptor responses were significantly hyperpolarizing, with an average equilibrium potential of -80.8mV.
In awake mice, however, these responses could be either hyperpolarizing or depolarizing, averaging at -63.9mV – a state known as the "[shunting](https://en.wikipedia.org/wiki/Shunting_inhibition)" regime.

Burman et al. hypothesized that the higher network activity in the awake state leads to a higher concentration of intracellular chloride, which in turn depolarizes the GABA<sub>A</sub> receptor equilibrium potential.
Anesthesia, by broadly suppressing neural activity, indirectly hyperpolarizes E<sub>GABA<sub>A</sub>R</sub>.
They confirmed this hypothesis by locally injecting an AMPA receptor antagonist ([NBQX](https://www.tocris.com/products/nbqx-disodium-salt_1044)) which suppressed network activity, and hyperpolarized E<sub>GABA<sub>A</sub>R</sub> to -78.0mV.

The Oxford researchers also hypothesized that changes in E<sub>GABA<sub>A</sub>R</sub> would lead to changes in network activity, resulting in a bi-directional relationship between the two quantities.

To test this hypothesis, Burman and Brodersen's team turned to the data from [Dandiset #000458](https://dandiarchive.org/dandiset/000458) – the very same dataset used by Claar et al.
By reanalyzing this data and manipulating a computational network model, they found that setting the E<sub>GABA<sub>A</sub>R</sub> parameter to the shunting regime (-60mV) reproduced spiking responses similar to those seen in awake mice.
Conversely, setting it to the hyperpolarizing regime (-80mV) mimicked the responses seen in anesthetized mice.
This data provides evidence for the hypothesized bidirectional relationship.

## Bridging Scales: From Synapses to Networks
Together, these two studies provide a rich, multi-level account of what happens to brain activity under anesthesia. They span from macroscale brain signals recorded by EEG all the way down to microscale synaptic responses from a single receptor type.
The population spiking data from [Dandiset #000458](https://dandiarchive.org/dandiset/000458) serves as a crucial bridge between these levels, allowing Burman et al. to explicitly connect their work to the broader field of anesthesia research.

However, it's important to note some key differences between the two studies. Claar et al. used isoflurane anesthesia and stimulated layers 5/6 of the cortex, while Burman et al. used urethane anesthesia and recorded from layer 2/3.
Additionally, while Claar et al. found the most dramatic differences between waking and anesthetized states around 180 ms after stimulation, Burman et al. focused their reanalysis on the initial spiking response within 15 ms of stimulation.

These differences highlight the potential for further reanalysis of [Dandiset #000458](https://dandiarchive.org/dandiset/000458).
Future studies could explore more similar experimental conditions, conduct a more thorough treatment of relevant response time periods, or investigate different aspects of anesthesia's effects altogether.

## Engaging with the Open Science Community
For those inspired by the work of Claar, Burman and Brodersen, and their teams, the journey doesn’t end here.
We encourage readers from all backgrounds to take advantage of this open science platform by publishing and reanalyzing data on DANDI.
We are confident that it will be a smooth and rewarding experience, but don't just take our word for it -- listen to what Dr. Leslie Claar and Dr. Paul Brodersen have to say,

> "After organizing our dataset into NWB format, validating and uploading our files was straightforward using a few simple commands from the DANDI Python Client. 
> The tools are well-documented, which made the process of uploading and publishing quite smooth. 
> Within a few months of publishing on DANDI, others were already interested in using our dataset."
> -- Dr. Leslie Claar

> “The DANDI archive is a fantastic resource with great tooling and exhaustive documentation. Its command line interface makes data retrieval and synchronization as simple as possible (but not simpler!).
> The standardized and well-documented formats for electrophysiological and neuroimaging data ensure that anyone can quickly find their way around a new archive without requiring extensive feedback from the authors that originally collected the data.
> These features make the DANDI archive a treasure trove of useful and re-usable data, unlike the unfortunately still commonplace unstructured data dumps on many other platforms or -- worst of all -- university servers.”
> -- Dr. Paul Brodersen and Professor Colin Akerman

To get you started on your own reanalysis project, we've prepared a Jupyter [notebook](https://github.com/dandi/example-notebooks/blob/master/000458/AllenInstitute/reanalysis.ipynb) demonstrating some basic reanalysis of [Dandiset #000458](https://dandiarchive.org/dandiset/000458).
This tool will help you dive right into the data, guiding you through the initial steps of exploration and analysis.

By engaging with this open science platform, you become part of a larger community of researchers who are building on each other's work and driving the field forward. In the world of open science, collaboration and curiosity drive discovery—so why not see where the data takes you?
