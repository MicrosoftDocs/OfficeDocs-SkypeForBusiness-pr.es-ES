---
title: 'Lync Server 2013: Definir las reglas de normalización'
TOCTitle: Definir las reglas de normalización
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48277079
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir las reglas de normalización en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Las reglas de normalización de Lync Server 2013 usan expresiones regulares de .NET Framework para traducir los números de teléfono marcados al formato E.164; es decir, las reglas de normalización obtienen el número de teléfono marcado por un usuario y convierten ese número al formato utilizado internamente por Lync Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.

Para ver los detalles sobre las reglas de normalización, consulte [Planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación sobre planeación.

Para más información sobre cómo escribir expresiones regulares, consulte "Expresiones regulares de .NET Framework" en [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).

Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:

  - Use la herramienta **Generar regla de normalización** para especificar los valores de los dígitos iniciales, la longitud, los dígitos que se quitarán y los que se agregarán; a continuación, deje que Panel de control de Lync Server genere por usted el patrón de coincidencia correspondiente y la regla de conversión.

  - Escribir manualmente las expresiones regulares para definir el patrón de coincidencia y la regla de conversión.

## En esta sección

  - [Crear o modificar una regla de normalización mediante Crear una regla de normalización en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Crear o modificar una regla de normalización manualmente en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

## Vea también

#### Tareas

[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

