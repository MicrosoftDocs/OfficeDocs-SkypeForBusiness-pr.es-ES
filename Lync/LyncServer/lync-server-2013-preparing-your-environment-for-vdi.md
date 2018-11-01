---
title: 'Lync Server 2013: Preparar su entorno para VDI'
TOCTitle: Preparar su entorno para VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48276185
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparar su entorno Lync Server 2013 para VDI

 

_**Última modificación del tema:** 2013-02-22_

Para preparar el entorno para el complemento de la VDI de Lync, siga estos pasos.

1.  En Lync Server 2013, asegúrese de que EnableMediaRedirection tiene el valor TRUE para todos los usuarios de VDI. Para obtener información detallada, vea los temas de ayuda relativos al cmdlet [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) y el cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy).

2.  En el equipo del centro de datos, instale el cliente de Lync 2013 en todos los equipos virtuales.

3.  En los equipos locales, instale el complemento de VDI de Lync.

