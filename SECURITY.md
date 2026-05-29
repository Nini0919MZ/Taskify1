# 🔒 Configuración de Seguridad - GEMINI API KEY

## ⚠️ IMPORTANTE - INSTRUCCIONES DE SEGURIDAD

Esta aplicación utiliza la API de Gemini. Para garantizar la seguridad de tu clave API:

### 1. **Configuración Inicial**

```bash
# Copia el archivo de plantilla
cp .env.example .env

# Edita .env y agrega tu clave de Gemini
# GEMINI_API_KEY=tu_clave_aqui
```

### 2. **Archivos Protegidos**

Los siguientes archivos **NUNCA** deben ser commiteados:
- `.env` - Variables de entorno (gitignored)
- `secrets.json` - Configuración sensible (gitignored)

Estos están en `.gitignore` y Git los ignorará automáticamente.

### 3. **Mejores Prácticas**

✅ **HACER:**
- Guardar la clave en `.env` local
- Usar `flutter_dotenv` para cargar variables
- Rotar la clave regularmente en Google Cloud Console
- Revocar claves comprometidas inmediatamente

❌ **NO HACER:**
- Hardcodear claves en el código
- Compartir el archivo `.env`
- Comprometer secretos a control de versiones
- Usar la misma clave en múltiples ambientes

### 4. **Flujo de Actualización de Clave**

Si tu clave fue comprometida:

1. Revoca la clave en [Google Cloud Console](https://console.cloud.google.com)
2. Genera una nueva clave
3. Actualiza `.env` localmente con la nueva clave
4. Haz `git filter-repo` para limpiar el historial (ver manual de git)
5. Haz `git push --force-with-lease`

### 5. **Para Nuevos Desarrolladores**

Si eres nuevo en el proyecto:

```bash
# Clona el repo
git clone <repo_url>
cd <project>

# Copia el archivo de plantilla
cp .env.example .env

# Pide la clave actual a un administrador
# (Nunca debe estar en commits o documentos públicos)

# Edita .env con la clave
nano .env

# Ahora puedes correr el proyecto
flutter pub get
flutter run
```

---

**Última actualización:** 2026-05-29
**Estado:** ✅ Seguridad implementada
