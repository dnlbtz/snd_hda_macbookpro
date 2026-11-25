ifdef PATCH_CIRRUS
snd-hda-codec-cirrus-objs :=	patch_cirrus.o
obj-$(CONFIG_SND_HDA_CODEC_CIRRUS) += snd-hda-codec-cirrus.o
else
snd-hda-codec-cs8409-objs :=    patch_cs8409.o patch_cs8409-tables.o
obj-$(CONFIG_SND_HDA_CODEC_CS8409) += snd-hda-codec-cs8409.o
endif

# The jack table is a linked list since "ALSA: hda: Use linked list for jack
# table" (7.3.6 and later) and an array before; the code needs to know which.
ifneq ($(shell grep -s jacktbl_last $(srctree)/include/sound/hda_codec.h),)
ccflags-y += -DHDA_JACK_LIST
endif
