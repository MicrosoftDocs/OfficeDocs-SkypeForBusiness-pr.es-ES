---
title: Quitar una entrada de host autorizada
TOCTitle: Quitar una entrada de host autorizada
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48275317
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar una entrada de host autorizada

 

_**Última modificación del tema:** 2012-09-26_

Este tema describe cómo eliminar una entrada autorizada de host heredada (conocida como una *entrada de aplicación de confianza* en Lync Server 2013). Debe quitar las entradas autorizadas de host para cualquier puerta de enlace SIP/CSTA de su implementación Office Communications Server 2007 R2 al migrar el control remoto de llamadas a una implementación de Lync Server 2013. Debe utilizar las herramientas administrativas incluidas en Office Communications Server 2007 R2 para quitar las entradas autorizadas del host existentes.

## Para quitar una entrada autorizada del host en una implementación Office Communications Server 2007 R2

1.  Abra la consola administrativa Office Communications Server 2007 R2.

2.  Expanda el árbol y haga clic con el botón secundario en el grupo en el que se creó el host autorizado.

3.  Haga clic en **Propiedades**y, a continuación, haga clic en **Propiedades del servidor front-end**.

4.  Haga clic en la pestaña **Autorización del host**.

5.  Seleccione un servidor y, a continuación, haga clic en **Quitar**.

6.  En **Propiedades**, haga clic en **Aceptar**.

