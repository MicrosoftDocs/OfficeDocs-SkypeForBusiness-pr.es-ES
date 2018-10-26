---
title: Actualización de la lista de habilitación de Outlook
TOCTitle: Actualización de la lista de habilitación de Outlook
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48275418
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Actualización de la lista de habilitación de Outlook

 

_**Última modificación del tema:** 2013-01-07_

Puede asegurarse de que el Complemento para conferencia en línea para Microsoft Lync 2013 siempre esté habilitado para los usuarios si crea una directiva que lo incluya en la lista de administración de complementos de Outlook. La directiva de lista de administración de complementos forma parte de los archivos de plantilla administrativa de Office de la Consola de administración de directivas de grupo. Esta directiva crea una clave del Registro en HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList. Puede agregar un valor para ucaddin.dll en esta clave y configurar el valor de ucaddin.dll de modo que siempre esté habilitado y los usuarios no puedan deshabilitarlo de forma manual.

## Para agregar ucaddin.dll a la lista de complementos de Outlook

  - Agregue el siguiente valor a la clave del Registro AddinList, ubicada en HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList:
    
      - Tipo de Registro = REG\_SZ
    
      - Nombre = ucaddin.dll
    
      - Valor = 1 (significa que el complemento siempre está habilitado y que el usuario final no puede administrarlo)

