---
title: 'Configuración de AD FS 2.0 para que sea compatible con la autenticación de clientes'
TOCTitle: Configuración de AD FS 2.0 para que sea compatible con la autenticación de clientes
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn308565(v=OCS.15)
ms:contentKeyID: 56271286
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de AD FS 2.0 para que sea compatible con la autenticación de clientes

 

_**Última modificación del tema:** 2016-12-08_

Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita autenticación con tarjetas inteligentes:

  - Autenticación basada en formularios (FBA)

  - Autenticación de cliente de seguridad de capa de transporte

Al usar la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse ya sea por medio de su nombre de usuario/contraseña o por medio de su tarjeta inteligente y PIN. Este tema se enfoca en cómo implementar la autenticación de cliente de seguridad de capa de transporte con AD FS 2.0. Para obtener más información acerca de los tipos de autenticación de AD FS 2.0, consulte el tema sobre AD FS 2.0: cómo cambiar el tipo de autenticación local en [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).


**Para configurar AD FS 2.0 para admitir la autenticación de cliente**

1.  Inicie sesión en el equipo con AD FS 2.0 mediante una cuenta de administrador de dominio.

2.  Inicie Windows Explorer.

3.  Vaya a C:\\inetpub\\adfs\\ls

4.  Haga una copia de seguridad del archivo web.config existente.

5.  Abra el archivo web.config existente con el Bloc de notas.

6.  Desde la barra de menús, seleccione **Editar** y, a continuación, seleccione **Buscar**.

7.  Busque **\<localAuthenticationTypes\>**.
    
    Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.

8.  Mueva la línea que contiene el tipo de autenticación TLSClient hacia la parte superior de la lista en la sección.

9.  Guarde y cierre el archivo web.config.

10. Inicie un símbolo del sistema con privilegios elevados.

11. Reinicie IIS ejecutando el siguiente comando:
    
        IISReset /Restart /NoForce

