---
title: Comprobación de la configuración de Office Web Apps Server en Lync Server 2013
TOCTitle: Comprobación de la configuración de Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48277193
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobación de la configuración de Office Web Apps Server en Lync Server 2013

 

_**Última modificación del tema:** 2014-04-22_

Después de agregar Office Web Apps Server a la topología y después de publicar la topografía, deberá ver dos nuevos eventos en el registro de eventos de Lync Server. En primer lugar, se debe haber agregado un evento LS Data MCU (Id. del evento 41034), el cual informa de que se ha detectado Office Web Apps Server:

**Se ha detectado el servidor de conferencias web WAC, habilitado para contenido de PowerPoint.**

Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:

**Detección WAC del servidor de conferencias web correcta.**

**Página presentador interno de WAC: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Página asistente interno de WAC: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Página de presentador externo de WAC: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Página de asistente interno de WAC: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Si ve un evento LS Data MCU con el Id. de evento 41033, indicará un error en la detección de Office Web Apps Server. En ese caso, Microsoft Lync Server 2013 intentará tantas veces como sea necesario detectar el servidor de aplicación web de Office recién configurado. Si el proceso de detección falla repetidas veces, deberá quitar Office Web Apps Server del documento de la topología, publicar la topología actualizada y, a continuación, cuando los problemas de conectividad estén resueltos, agregar de nuevo Office Web Apps Server a la topología.

Si Office Web Apps Server parece correctamente configurado y ha sido reconocido por el proceso de detección, puede verificar que funciona debidamente compartiendo una presentación de PowerPoint entre un par de clientes Microsoft Lync 2013. Si el usuario A puede cargar y visualizar la presentación de PowerPoint y el usuario B puede unirse a la reunión y ver esa presentación, significa que Office Web Apps Server funciona.

Aún cuando parezca que Office Web Apps Server está correctamente configurado, podría recibir el mensaje de error "Algunas características de uso compartido no están disponibles debido a problemas de conectividad del servidor” cuando intente compartir una presentación de PowerPoint.Si recibe ese mensaje de error, reinicie el servidor (o servidores) front-end asociado al nuevo servidor Office Web Apps Server.

