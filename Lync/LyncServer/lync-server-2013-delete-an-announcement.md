---
title: Eliminar un anuncio
TOCTitle: Eliminar un anuncio
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49889010
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un anuncio

 

_**Última modificación del tema:** 2012-11-01_

Use el siguiente procedimiento para eliminar un anuncio que se usa para llamadas a números no asignados.

## Para eliminar un anuncio

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Muestre todos los anuncios de su organización. En la línea de comandos, ejecute:
    
        Get-CsAnnouncement

4.  En la lista resultante, busque el anuncio que desea eliminar, y copie el GUID. A continuación, en la línea de comandos, ejecute:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    Por ejemplo:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    

    > [!NOTE]
    > Para obtener detalles acerca de más opciones, vea <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> y <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.



## Vea también

#### Tareas

[Crear un anuncio en Lync Server 2013](lync-server-2013-create-an-announcement.md)  

#### Otros recursos

[Remove-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement)  
[Get-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement)

