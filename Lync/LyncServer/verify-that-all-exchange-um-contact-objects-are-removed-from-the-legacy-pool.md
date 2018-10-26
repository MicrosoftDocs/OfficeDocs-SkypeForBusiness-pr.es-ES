---
title: "Objetos de contacto de mensajería unif. de Exchange quitados de grupo de servidores"
TOCTitle: "Vérif. de la suppr. des objets de contact de mess. Un. Exchange du pool hérité"
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49889198
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar que todos los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo de servidores heredado

 

_**Última modificación del tema:** 2012-09-26_

Use la herramienta **OCSUmUtil** o el cmdlet **Get-CsExumContact** para comprobar que se han eliminado objetos de contacto de mensajería unificada de Exchange del grupo de Office Communications Server 2007 R2 heredado. **OCSUmUtil** se encuentra en la siguiente carpeta:

%Archivos de programa%\\Archivos comunes\\Lync Server 2013\\Support\\OcsUMUtil.exe

**OCSUmUtil** debe ejecutarse desde una cuenta de usuario que tenga:

  - Pertenencia a los grupos RTCUniversalServerAdmins y RTCUniversalUserAdmins (que incluyen derechos para leer la configuración de mensajería unificada de Exchange Server)

  - Derechos de dominio para crear objetos de contacto en el contenedor especificado de la unidad organizativa.

Para detalles sobre cómo usar el cmdlet **Get-CsExumContact**, vea [Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact) en la documentación de Shell de administración de Lync Server.

