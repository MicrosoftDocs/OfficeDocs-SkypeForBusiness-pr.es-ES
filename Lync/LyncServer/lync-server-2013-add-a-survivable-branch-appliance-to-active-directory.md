---
title: 'Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory'
TOCTitle: Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48275018
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-23_

Si piensa implementar una Aplicación de sucursal con funciones de supervivencia, debe agregar la Aplicación de sucursal con funciones de supervivencia a los Servicios de dominio de Active Directory. Realice este procedimiento en el sitio central.

> [!IMPORTANT]  
> Realice este procedimiento únicamente si implementa una Aplicación de sucursal con funciones de supervivencia. No lo realice si implementa un Servidor de sucursal con funciones de supervivencia.



## Para agregar una aplicación de sucursal con funciones de supervivencia a los Servicios de dominio de Active Directory

1.  Inicie sesión en un servidor miembro como miembro del grupo Administradores de organización.

2.  Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Usuarios y equipos de Active Directory**.

3.  En el menú **Acciones**, haga clic en **Nuevo** y, a continuación, en **Equipo**.

4.  En el cuadro de diálogo **Nuevo objeto - Equipo**, escriba el nombre del objeto de equipo de la Aplicación de sucursal con funciones de supervivencia (por ejemplo, BranchOffice1) y haga clic en **Cambiar**.

5.  En el cuadro de diálogo **Seleccionar usuario o grupo**, agregue el grupo RTCUniversalSBATechnicians y haga clic en **Aceptar**.
    

    > [!NOTE]
    > Más adelante, un miembro del grupo RTCUniversalSBATechnicians del sitio de sucursal agregará este dispositivo al dominio.



6.  Haga clic en **Aceptar** para guardar el objeto de equipo de la Aplicación de sucursal con funciones de supervivencia.

7.  Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Editor ADSI**.

8.  En el **Editor ADSI**, haga clic con el botón secundario en el objeto de equipo que creó en los pasos anteriores y, a continuación, haga clic en **Propiedades**.

9.  En la lista de atributos, haga clic en **servicePrincipalName** y luego en **Editar**.

10. En el campo **Valor para agregar**, escriba HOST/\<SBA FQDN\>, donde \<FQDN SBA\> corresponde al nombre de dominio completo (FQDN) de la Aplicación de sucursal con funciones de supervivencia. Por ejemplo, escriba **HOST/BranchOffice1.contoso.com** .

11. Haga clic en **Aceptar** para guardar la configuración de atributo **servicePrincipalName** y, a continuación, en **Aceptar** para guardar las propiedades del objeto de equipo.

12. En **Usuarios y equipos de Active Directory**, haga clic con el botón secundario en **Usuarios**, haga clic en **Nuevo** y, a continuación, en **Usuario**.

13. Introduzca información en el asistente para crear una cuenta de usuario de dominio para un técnico de la Aplicación de sucursal con funciones de supervivencia.

14. En **Usuarios y equipos de Active Directory**, haga clic en **Usuarios**, haga clic con el botón secundario en el objeto de equipo y luego haga clic **Agregar a un grupo**.

15. En **Escribir los nombres de objeto para seleccionar**, escriba **RTCUniversalSBATechnicians** y haga clic en **Aceptar**.

16. Repita los pasos 12-15 para cada técnico del sitio de sucursal.

**Siguiente paso**: [Agregar sitios de sucursal a la topología en Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

