---
title: Presentación del identificador del destinatario de la llamada en Lync Server 2013
TOCTitle: Presentación del identificador del destinatario de la llamada en Lync Server 2013
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49889694
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Presentación del identificador del destinatario de la llamada en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Con Lync Server 2010, el número de teléfono que recibe la llamada (es decir, el número de teléfono al que se llama) se puede traducir del formato E.164 al formato de marcado local que el *tronco de mismo nivel* necesita (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

> [!IMPORTANT]  
> La capacidad para asociar una o varias reglas de traslación a una configuración de tronco de Telefonía IP empresarial ha sido diseñada para usarla como <em>alternativa</em> a la configuración de las reglas de traslación en el tronco de mismo nivel. No asocie las reglas de traslación a una configuración de tronco Telefonía IP empresarial si ha configurado reglas de conversión en el tronco de mismo nivel porque las dos reglas podrían entrar en conflicto.



Use uno de los métodos siguientes para crear o modificar una regla de traslación:

  - Use la herramienta **Crear una regla de conversión** para especificar valores para los dígitos de inicio, la longitud, los dígitos que deben quitarse y los que deben agregarse y después, deje que Panel de control de Lync Server genere en su lugar el patrón de comprobación correspondiente y la regla de traslación.

  - Escriba expresiones regulares manualmente para definir el patrón de comparación y la regla de traslación.


> [!NOTE]
> Para más información sobre la escritura de expresiones regulares, vea la sección sobre "Expresiones regulares de .NET Framework" en <A href="http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=140927&amp;clcid=0xC0A</A>.



## En esta sección

  - [Crear o modificar una regla de conversión mediante la herramienta Generar una regla de conversión](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Crear o modificar una regla de conversión manualmente](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

## Vea también

#### Conceptos

[Presentación del id. de autor de llamada en Lync Server 2013](lync-server-2013-caller-id-presentation.md)

