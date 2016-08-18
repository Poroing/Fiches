FORMAT = pdf
LATEXMK = latexmk -$(FORMAT)

OUTDIR = ../../Fiches

TARGET_FICHES = espacePrehilbertienReelle arithmetique  \
	fonctionDUneVariableRelle suite matrice structures \
	integration derivabilite equationDifferentielle \
	espaceVectoriel polynomes serie

#Log and build files
TOC_FILES = $(addsuffix .toc,$(TARGET_FICHES))
LOG_FILES = $(addsuffix .log,$(TARGET_FICHES))
OUT_FILES = $(addsuffix .out,$(TARGET_FICHES))
FLS_FILES = $(addsuffix .fls,$(TARGET_FICHES))
FDB_LATEXMK_FILES = $(addsuffix .fdb_latexmk,$(TARGET_FICHES))
AUX_FILES = $(addsuffix .aux,$(TARGET_FICHES))

OUT_DOCUMENTS = $(addsuffix .$(FORMAT),$(TARGET_FICHES))

FICHES = $(addprefix $(OUTDIR)/,$(OUT_DOCUMENTS))

REMOVABLE_FILES = $(TOC_FILES) $(LOG_FILES) $(OUT_FILES) $(FLS_FILES) \
	$(AUX_FILES) $(FDB_LATEXMK_FILES)

.PHONY: all clean

all: $(FICHES)

$(OUTDIR)/%.pdf : %.tex skeleton.tex
	$(LATEXMK) $<
	mv $(@F) $@

clean:
	rm -f $(REMOVABLE_FILES)
