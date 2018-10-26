---
title: "Lync Server 2013 : Conf. des numéros d’accès aux conférences rendez-vous"
TOCTitle: Configurar números de conferencia de acceso telefónico
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48276849
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar números de conferencia de acceso telefónico en Lync Server 2013

 

_**Última modificación del tema:** 2011-07-17_

Cuando se implementa la característica de conferencia de acceso telefónico local, es necesario establecer números de teléfono que los usuarios puedan marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias. Estos números de acceso telefónico se muestran en invitaciones a reuniones y en la página web de configuración de conferencia de acceso telefónico local.

Antes de crear números de acceso telefónico, debe planear las regiones de conferencia de acceso telefónico local y, a continuación, configurar planes de marcado con las regiones. Para obtener información detallada sobre las regiones, consulte [Planeación de las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación de planeación. Si desea información detallada sobre la configuración de planes de marcado para las conferencias de acceso telefónico, consulte [Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).


> [!NOTE]
> No puede usar un nuevo número de acceso telefónico hasta que se complete la replicación de Servicios de dominio de Active Directory (AD&nbsp;DS) de ese número de acceso telefónico. La replicación puede prolongarse durante varias horas.




> [!NOTE]
> Una vez creados los números de acceso telefónico, puede modificar el nombre para mostrar de los objetos de contacto de Active Directory, de modo que los usuarios puedan identificar con mayor facilidad el número de acceso correcto. Use el cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> para modificar el nombre para mostrar. No modifique los objetos de Active Directory manualmente. Para más información sobre la modificación de un número de acceso, consulte la documentación del Shell de administración de Lync Server para el cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG>.



## En esta sección

[Crear o modificar un número de acceso para conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

## Vea también

#### Conceptos

[Planeación de las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  

#### Otros recursos

[Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

