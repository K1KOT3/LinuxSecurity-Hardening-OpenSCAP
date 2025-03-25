# Bastionado de Sistemas y Auditoría con OpenSCAP

🔒 **Fortalecimiento de la seguridad en sistemas Linux mediante auditoría y aplicación de configuraciones seguras**  

Este repositorio contiene el informe del **Laboratorio de Bastionado de Sistemas (FSSC)**, donde se han aplicado técnicas de **seguridad en servidores Linux (CentOS y Fedora)** utilizando herramientas manuales y automatizadas como **OpenSCAP** para verificar y reforzar la configuración del sistema.

## 🔍 Descripción

El objetivo de esta práctica es evaluar y mejorar la **seguridad de sistemas operativos Linux** mediante la aplicación de controles de bastionado, identificando configuraciones inseguras y corrigiéndolas con soluciones automatizadas.

Las principales tareas realizadas incluyen:
- **Auditoría de seguridad en CentOS 7** usando la guía CIS Benchmark.
- **Aplicación manual de configuraciones seguras** en módulos del kernel, permisos de archivos, servicios y autenticación.
- **Verificación automatizada de seguridad con OpenSCAP** en Fedora.
- **Generación de informes de cumplimiento y remediación de vulnerabilidades**.

## 📁 Contenido del Repositorio

- `Practica 4 LAB Paula y Enrique.pdf` → Informe completo con configuración, auditoría y mitigaciones aplicadas.
- **Scripts de hardening y configuración automática** (próximamente).

## 🛠 Herramientas Utilizadas

### 🔹 **Bastionado Manual en CentOS 7**
- **Aplicación de la Guía CIS Benchmark**:
  - Deshabilitación de módulos inseguros (`cramfs`, `freevxfs`).
  - Configuración de permisos en `/tmp` con `nodev`.
  - Activación de `gpgcheck` en `yum` para verificar firmas de paquetes.
  - Configuración del banner de advertencia en `issue` para inicio de sesión.
  - Sincronización de tiempo con `chrony` (`rpm -q chrony`).
  - Habilitación y verificación de `firewalld`.

### 🔹 **Auditoría Automática con OpenSCAP en Fedora**
- **Verificación de cumplimiento con estándares de seguridad**:
  - **SCAP 1.3**, **XCCDF 1.2**, **OVAL 5.11.1**, **CPE 2.3**.
  - Evaluación de configuración del sistema (`oscap info`).
  - Escaneo de seguridad (`oscap xccdf eval`).
- **Identificación de vulnerabilidades**:
  - Configuraciones incorrectas en permisos de archivos (`RPMVerify`).
  - Políticas de contraseñas débiles (`PAM`, `password aging`).
  - Servicios innecesarios habilitados (`bind`, `sshd root login`).
  - Falta de auditoría de accesos (`auditd` y `AIDE`).

## 🚀 Resultados y Hallazgos

| Control Evaluado  | Estado Inicial | Estado Final |
|------------------|--------------|-------------|
| **Módulos inseguros deshabilitados** | ❌ No aplicado | ✅ Aplicado |
| **Configuración de `/tmp` con `nodev`** | ❌ Incorrecta | ✅ Corregida |
| **Firma de paquetes (`gpgcheck`) activada** | ✅ Correcta | ✅ Correcta |
| **Firewall (`firewalld`) activado** | ❌ Desactivado | ✅ Activado |
| **Políticas de contraseña seguras (`PAM`)** | ❌ Incorrectas | ⚠️ Parcialmente corregidas |
| **Verificación de logs (`auditd`)** | ❌ Incompleta | ⚠️ Parcialmente corregida |

📊 **Nivel de Cumplimiento Inicial:** **43.61%**  
📈 **Nivel de Cumplimiento Tras Ajustes:** **52.48%**

## 📌 Posibles Mejoras

- **Automatización de la corrección de configuraciones** con scripts Bash/Ansible.
- **Uso de perfiles de seguridad más estrictos** en OpenSCAP.
- **Integración con herramientas como Lynis o SELinux** para auditoría avanzada.
- **Refuerzo de políticas de autenticación** con MFA y SSH hardening.

## 🤝 Contribuciones

Si deseas mejorar este análisis, agregar nuevas configuraciones o expandir la automatización, haz un **fork**, añade tus cambios y envía un **Pull Request**.

## 📜 Licencia

Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.
