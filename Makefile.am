-include $(top_srcdir)/build/modmake.rulesam
AUTOMAKE_OPTIONS = foreign subdir-objects
MODNAME=mod_telnyx_video

LIBS := $(if $(switch_builddir),$(switch_builddir)/libfreeswitch.la,)

mod_LTLIBRARIES = mod_telnyx_video.la
mod_telnyx_video_la_SOURCES  = globals.c cJSON.c http.c api.c servers.c hash.c mod_telnyx_video.c
mod_telnyx_video_la_CFLAGS   = $(AM_CFLAGS) $(FREESWITCH_CFLAGS) -DJANUS_CONFIG_FILE=\"telnyx_video.conf\"
mod_telnyx_video_la_LDFLAGS  = -avoid-version -module -no-undefined -shared $(FREESWITCH_LIBS) $(OPENSSL_LIBS) $(MOSQUITTO_LIBS)
mod_telnyx_video_la_LIBADD   = $(LIBS)

print_tests:
	@set +e; \
	test -z "$(TESTS)" || for i in $(TESTS); do echo $(subdir)/$$i; done;
