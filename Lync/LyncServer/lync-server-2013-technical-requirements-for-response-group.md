---
title: 'Lync Server 2013: Requisitos técnicos para grupos de respuesta'
TOCTitle: Requisitos técnicos para grupos de respuesta
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48275154
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para grupos de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En esta sección se describen los siguientes requisitos técnicos de la Aplicación de grupo de respuesta:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de los puertos

  - Requisitos de archivos de audio

  - Requisitos de la herramienta de configuración de Grupo de respuesta

## Requisitos de hardware

Los requisitos de hardware de la Aplicación de grupo de respuesta son los mismos que los de Servidores front-end. Encontrará más información sobre los requisitos de hardware, consulte [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.

## Requisitos de software

Los requisitos de sistema operativo y requisitos previos de software de la Aplicación de grupo de respuesta son los mismos que los de Servidores front-end. Encontrará más información sobre los requisitos de software, consulte [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

Si usa archivos de Windows Media Audio (.wma) para la música y los anuncios de Grupo de respuesta, todos los Servidores front-end o servidores de Standard Edition que ejecuten el Aplicación de grupo de respuesta deben tener instalado el tiempo de ejecución de Windows Media Format en servidores que ejecuten Windows Server 2008 R2 o Microsoft Media Foundation en servidores que ejecuten Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows.

Para más detalles sobre los requisitos de audio, vea "Requisitos de archivos de audio" más adelante en esta sección.

## Requisitos de los puertos

Aplicación de grupo de respuesta usa los siguientes puertos:

  - **Puerto 5071**   Se utiliza para solicitudes de escucha SIP

  - **Puerto 8404**   Se utiliza para las comunicaciones entre servidores
    

    > [!NOTE]
    > Este puerto se usa para el servicio de correspondencia activo y es necesario cuando la Aplicación de grupo de respuesta se implementa en un grupo de servidores que tiene más de un Servidor front-end.




> [!NOTE]
> Estos puertos son configuraciones predeterminadas que se pueden cambiar mediante el cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para información sobre este cmdlet, vea la documentación de Shell de administración de Lync Server.



## Requisitos de archivos de audio

Aplicación de grupo de respuesta admite el formato de archivo de onda (.wav) y el formato de archivo de audio Windows Media (.wma) para mensajes de Grupo de respuesta, música en espera o preguntas de respuesta interactiva de voz (IVR).

El formato de archivo de audio Windows Media necesita que esté instalado Tiempo de ejecución de Windows Media Format en el Servidores front-end que ejecuta Windows Server 2008 R2 y Windows Server 2008. Para más información, vea "Requisitos de software" anteriormente en esta sección.

## Formatos de archivo wave compatibles

Todos los archivos wave deben cumplir los requisitos siguientes:

  - Archivo de 8 bits o de 16 bits

  - Formato de modulación lineal por impulsos codificados (LPCM), A-Law o mu-Law

  - Mono o estéreo

  - 4 MB o menos

Para obtener el máximo rendimiento de los archivos wave, se recomienda usar un archivo wave mono de 16 bits a 16 kHz.

## Formatos de archivo de audio Windows Media admitidos

Si usa un archivo de audio Windows Media, considere la posibilidad de usar velocidades de bits lentas y compruebe el rendimiento del sistema cuando se somete a carga.

Puede usar Microsoft Expression Encoder 4 para convertir un archivo al formato de audio de Windows Media. Para descargar Expression Encoder 4, vea [http://go.microsoft.com/fwlink/?linkid=202843\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=202843%26clcid=0xc0a).

## Requisitos para la herramienta de configuración del grupo de respuesta

Herramienta de configuración de grupo de respuesta admite combinaciones de los sistemas operativos y los exploradores web que se describen en la tabla siguiente.


> [!NOTE]
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.



### Sistemas operativos y exploradores web compatibles

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operativo</th>
<th>Explorador web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista con Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 con Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p></p>
<p></p>
<p></p>
<p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
</tbody>
</table>


## Consola del agente del grupo de respuesta

La consola de agente admite combinaciones de los sistemas operativos y los exploradores web que se describen en la tabla siguiente.


> [!NOTE]
> Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.



### Sistemas operativos y exploradores web compatibles

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operativo</th>
<th>Explorador web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista con Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 con Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modo nativo)</p>
<p>Internet Explorer 9 (modo nativo)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td></td>
</tr>
</tbody>
</table>

