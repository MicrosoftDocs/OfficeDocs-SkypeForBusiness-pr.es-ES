---
title: "Lync Server 2013: Comprobar reglas de normalización para estacionamiento de llamadas"
TOCTitle: Comprobar las reglas de normalización para el estacionamiento de llamadas
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48276927
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar las reglas de normalización para el estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-11_

Las órbitas de Estacionamiento de llamadas no deben normalizarse. Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados. Si debe crear una regla de normalización adicional para evitar que las órbitas se normalicen, siga el procedimiento descrito en [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) para definir una regla de normalización nueva, como que el **Patrón con el que hacer coincidir** identifica el intervalo de órbita y el **Patrón de traducción** es **$1**. Por ejemplo, si su intervalo de órbitas de Estacionamiento de llamadas es 7000 – 7999, el **Patrón con el que hacer coincidir** es **^(7\\d{3})$** y el **Patrón de traducción** es **$1**.

> [!IMPORTANT]  
> Compruebe que la regla de normalización predeterminada de sus planes de marcado no contenga <strong>^(\d*)</strong>. De lo contrario, la regla de normalización de Estacionamiento de llamadas no se ejecutará.



## Vea también

#### Tareas

[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

