---
title: Comprobar las comunicaciones con un cliente de Lync Online
TOCTitle: Comprobar las comunicaciones con un cliente de Lync Online
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48276643
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar las comunicaciones con un cliente de Lync Online

 

_**Última modificación del tema:** 2016-12-08_

Para permitir a usuarios de Lync de la organización comunicarse con usuarios de un cliente de Microsoft Lync Online 2010, primero debe completar los siguientes pasos:

  - Reunir todos los requisitos previos. Este paso incluye implementar los servidores internos y perimetrales, habilitar la compatibilidad con federación para la organización, y configurar cuentas de usuario. Para más información, consulte [Requisitos previos para federar con un cliente de Lync Online](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Configurar compatibilidad con acceso a dominio en la implementación interna. Este paso incluye crear una entrada de proveedor de host y configurar la implementación para permitir el acceso desde el dominio del cliente de Lync Online. Para más información, consulte [Configurar compatibilidad de federación para un dominio de Lync Online](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Configurar sus cuentas de usuario para admitir federación. Para más información, consulte [Configurar acceso de usuario para federación con un cliente de Lync Online](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Una vez que haya completado todos estos pasos y para el administrador de cliente de Lync Online 2010 complete toda configuración de los servicios en línea para admitir federación con su organización, pruebe las comunicaciones entre un usuario interno de la organización y un usuario del cliente de Lync Online para verificar las comunicaciones. Si la comunicación no es correcta, use la Herramienta de registro desde su servidor perimetral para capturar los archivos de registro y seguimiento a fin de solucionar el problema. Para más información sobre el uso de la Herramienta de registro, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md) en la documentación sobre operaciones. Para más información sobre la Herramienta de registro, consulte la documentación de la Herramienta de registro de Lync Server 2010 en la Biblioteca de TechNet en [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265%26clcid=0xc0a).

