---
title: "Lync Server 2013: Colocación de servidores compatibles en componentes perimetrales"
TOCTitle: Colocación de servidores compatibles en componentes perimetrales
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48275114
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Colocación de servidores compatibles en componentes perimetrales en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

El servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V están colocados encuentran en el mismo servidor. Los siguientes componentes perimetrales no se pueden colocar juntos ni con ningún otro rol de servidor de Servidores perimetrales:

  - Servidor perimetral

  - Director (Optativo)

  - Proxy inverso

> [!IMPORTANT]  
> No es necesario que el proxy inverso esté dedicado solo a servir a Lync Server 2013. Por ejemplo, puede proporcionar servicios para publicar los servicios web de Lync Server y simultáneamente proporcionar un sitio web publicado en otro sitio web que no tiene ninguna relación con Lync Server. Si ya dispone de un servidor proxy inverso en la red perimetral por compatibilidad con otros servicios, puede usarlo en Lync Server 2013.


