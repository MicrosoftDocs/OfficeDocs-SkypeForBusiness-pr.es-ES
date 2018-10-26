---
title: Configuración de los Servicios de federación de Active Directory (AD FS) 2.0
TOCTitle: Configuración de los Servicios de federación de Active Directory (AD FS) 2.0
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn308561(v=OCS.15)
ms:contentKeyID: 56271264
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de los Servicios de federación de Active Directory (AD FS) 2.0

 

_**Última modificación del tema:** 2016-12-08_

En la siguiente sección se describe cómo configurar los servicios de federación de Active Directory (AD FS 2.0) para admitir autenticación multifactor. Para obtener información acerca de cómo instalar AD FS 2.0, consulte las guías paso a paso y de procedimientos de AD FS 2.0 en [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).


> [!NOTE]
> Al instalar AD FS 2.0, no use Windows Server Manager para agregar el rol de los servicios de federación de Active Directory. En su lugar, descargue e instale el paquete 2.0 RTW de los servicios de federación de Active Directory en <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.




**Para configurar AD FS para la autenticación en dos fases**

1.  Inicie sesión en el equipo con AD FS 2.0 mediante una cuenta de administrador de dominio.

2.  Inicie Windows PowerShell.

3.  Desde la línea de comandos de Windows PowerShell, ejecute el siguiente comando:
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  Establezca una colaboración con cada Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: servidores Director, Enterprise Pool y Standard Edition de julio de 2013 que se habilitarán para la autenticación pasiva ejecutando el siguiente comando, que reemplazará el nombre de servidor específico a la implementación:
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Desde el menú Herramientas administrativas, inicie la consola de administración de AD FS 2.0.

6.  Expanda **Relaciones de confianza** \> **Relaciones de confianza para usuario autenticado**.

7.  Compruebe que se haya creado una nueva relación de confianza para el Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: servidores Enterprise Pool o Standard Edition, julio de 2013.

8.  Cree y asigne una regla de autorización de emisión para la relación de confianza para usuario autenticado mediante Windows PowerShell ejecutando los siguientes comandos:

```    
$IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
```
    
```
Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
```

9.  Cree y asigne una regla de transformación de emisión para la relación de confianza para usuario autenticado mediante Windows PowerShell ejecutando los siguientes comandos:

```    
$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
```

```
Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
```

10. Desde la consola de administración de AD FS 2.0, haga clic con el botón secundario en la relación de confianza para usuario autenticado y seleccione **Editar reglas de notificaciones**.

11. Seleccione la pestaña **Reglas de autorización de emisión** y compruebe que la nueva regla de autorización se haya creado correctamente.

12. Seleccione la pestaña **Reglas de transformación de emisión** y compruebe que la nueva regla de transformación se haya creado correctamente.

