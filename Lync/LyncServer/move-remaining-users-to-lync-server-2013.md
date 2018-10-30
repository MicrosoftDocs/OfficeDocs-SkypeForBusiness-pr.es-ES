---
title: Mover los usuarios restantes a Lync Server 2013
TOCTitle: Mover los usuarios restantes a Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49889226
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover los usuarios restantes a Lync Server 2013

 

_**Última modificación del tema:** 2012-09-29_

Puede migrar usuarios a la nueva implementación de Lync Server 2013 con el Panel de control de Lync Server o el Shell de administración de Lync Server. Es preciso que cumpla algunos requisitos para garantizar que la transición a Lync Server 2013 se realice sin problemas. Para más información sobre los requisitos previos para completar los procedimientos descritos en este tema, vea [Configurar clientes para migración](configure-clients-for-migration.md). Para ver los pasos detallados para migrar usuarios, vea [Fase 4: Mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md).

> [!IMPORTANT]  
> No puede usar el complemento Usuarios y equipos de Active Directory o las herramientas administrativas de Lync Server 2010 para desplazar usuarios de los entornos heredados a Lync Server 2013.



Al migrar usuarios a un grupo de servidores de Lync Server 2013, los datos de los usuarios se migran a la base de datos back-end asociada al nuevo grupo.

> [!IMPORTANT]  
> Estos datos incluyen las reuniones activas creadas por el usuario heredado. Por ejemplo, si un usuario heredado configuró una conferencia del tipo <strong>mi reunión</strong> , esa conferencia seguirá disponible en el nuevo grupo de servidores de Lync Server 2013 tras migrar el usuario. El acceso a esa reunión estará determinado por los mismos detalles de <strong>URL de conferencia e ID de conferencia</strong> . La única diferencia es que la conferencia ahora se hospedará en el grupo de servidores de Lync Server 2013, en vez del grupo de servidores de Lync Server 2010.




> [!NOTE]
> Para hospedar usuarios en Lync Server 2013 no es necesario implementar clientes actualizados a la vez. La funcionalidad nueva estará disponible para los usuarios únicamente cuando hayan actualizado al nuevo software cliente.



## Tarea posterior a la migración

1.  Tras migrar los usuarios, compruebe la directiva de conferencia que tienen asignada.

2.  Para garantizar que las reuniones organizadas por usuarios hospedados en Lync Server 2013 funcionen sin problemas con los usuarios federados hospedados en Lync Server 2010, la directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.

3.  Las directivas de conferencia que permiten participantes anónimos tienen seleccionada la opción **Permitir a los participantes invitar a usuarios anónimos** en el Panel de control de Lync Server 2013 y tienen la opción **AllowAnonymousParticipantsInMeetings** definida como **True** en el resultado del cmdlet **Get-CsConferencingPolicy** del Shell de administración de Lync Server.

4.  Para más información sobre cómo configurar la directiva de conferencia con el Shell de administración de Lync Server, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingPolicy) en la documentación del Shell de administración de Communications Server.

