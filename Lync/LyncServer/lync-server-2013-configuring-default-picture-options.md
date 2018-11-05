---
title: Configuración de opciones predeterminadas de imagen
TOCTitle: Configuración de opciones predeterminadas de imagen
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn205074(v=OCS.15)
ms:contentKeyID: 53901786
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de opciones predeterminadas de imagen

 

_**Última modificación del tema:** 2013-03-22_

De forma predeterminada, se muestran las imágenes de los usuarios. Si los usuarios quieren ocultar su imagen, pueden elegir la opción **Ocultar mi foto** en el cliente Lync. No obstante, algunas de las demás aplicaciones de Office hacen caso omiso de esta configuración.

Si el hecho de que las imágenes se puedan mostrar aunque el usuario las desactive constituye un problema, puede cambiar la configuración de visualización de imágenes de Lync de forma global o en un sitio o servicio, de modo que las imágenes de los usuarios no se muestren de forma predeterminada. Utilice el siguiente cmdlet de Shell de administración de Lync Server para que las imágenes de los usuarios solo se muestren si ellos eligen expresamente la opción **Mostrar mi foto** en el cliente:

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Para obtener más información sobre este cmdlet, consulte la [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration) en la documentación del Shell de administración de Lync Server.

