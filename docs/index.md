---
hide:
  - navigation
  - toc
  - title
---
# Home

<div style="display: flex; align-items: center; gap: 20px;">

<!-- Text Content -->
<div style="flex: 1; text-align: justify;"><p>
  <b>Sonic Avionics</b> is a research organization that focuses on building flight computers.
</p>
<p>
  All hardware and code is on <a href="https://github.com/sonicavionics/4in">GitHub</a>.
</p>
<p>
  Hardware will be sold as a kit once it's ready.
</p>
<p>
  We are currently working on a 4 inch diameter avionics system for high powered model rockets. 
</p>
</div>

<!-- Model Viewer -->
<model-viewer 
  src="model/ImageToStl.com_board.front.glb" 
  alt="3D model of a board"
  auto-rotate 
  camera-controls 
  poster="model/poster.webp" 
  touch-action="pan-y"
  style="width: 30%; height: 300px;">
</model-viewer>

</div>

<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>

<!-- <figure markdown="span">

  ![alt text](img/IMG_0629.jpg){ width="300" }
  <figcaption>Zeul</figcaption>

</figure> -->

<div style="text-align: center;">

<style>
/* Disable background highlight on hover */
table tr:hover, table td:hover {
  background-color: transparent !important;
}

/* Prevent text selection when hovering */
table, table * {
  user-select: none;
}
</style>
<table style="margin: 0 auto;">
  <tr>
      <td align="center" style="vertical-align: middle;">
      <img src="https://raw.githubusercontent.com/sonicavionics/4in-sensors/refs/heads/main/images/board.front.png" width="300" /><br>
      <a href="/avionics/PCB-Modules/sensors/">Sensor Module 0.1.0</a>
    </td>
      <td align="center" style="vertical-align: middle;">
      <img src="/avionics/cad/thumbnail.png" width="250" /><br>
      <a href="avionics/cad/">Avionics CAD</a>
    </td>
      <td align="center" style="vertical-align: middle;">
      <img src="/avionics/modules/power/0_0_2/thumbnail.jpg" width="300" /><br>
      <a href="/avionics/PCB-Modules/power/0_0_2/">Power Module 0.0.2</a>
    </td>

</table>
</div>
