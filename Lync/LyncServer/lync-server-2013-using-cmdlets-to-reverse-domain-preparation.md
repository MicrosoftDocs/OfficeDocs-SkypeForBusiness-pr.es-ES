---
title: 'Lync Server 2013: Uso de cmdlets para revertir la preparación del dominio'
TOCTitle: Uso de cmdlets para revertir la preparación del dominio
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48274235
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso de cmdlets para revertir la preparación del dominio para Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

Use el cmdlet **Disable-CsAdDomain** para revertir el paso de preparación del dominio.

## Usar cmdlets para revertir la preparación del dominio

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo Admins. del dominio.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Por ejemplo:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Si el parámetro Force está presente, se revierte la preparación del dominio, aunque uno o más Servidores front-end o Servidores de conferencia A/V del dominio estén activados. Si el parámetro Force no está presente, la reversión de la preparación del dominio se termina si cualquier Servidores front-end o Servidores de conferencia A/V del dominio están activados.
    

    > [!NOTE]
    > El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se guarda en el contenedor del sistema (habitual en implementaciones de actualización cuya configuración global no se ha migrado al contenedor de configuración), deberá definir un controlador de dominio en la raíz del bosque de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet da por sentado que la configuración se guarda en el contenedor de configuración y hace referencia a cualquier controlador de dominio de AD&nbsp;DS.



## Vea también

#### Tareas

[Ejecutar la preparación del dominio para Lync Server 2013](lync-server-2013-running-domain-preparation.md)  

#### Otros recursos

[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)

