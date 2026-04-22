# Define variables for easier maintenance
DOCNAME = tutorial
MAIN_TEX = $(DOCNAME).tex
TARGET = $(DOCNAME).pdf

COMPILER = latexmk
FLAGS = -pdf -shell-escape -file-line-error -interaction=nonstopmode -f

# .PHONY tells make that these targets don't represent actual files
.PHONY: all clean distclean watch

# Default target
all: $(TARGET)

# Compile the document
# The $< variable automatically refers to the first prerequisite (MAIN_TEX)
$(TARGET): $(MAIN_TEX)
	$(COMPILER) $(FLAGS) $<

# Continuously watch and recompile on changes
watch:
	$(COMPILER) $(FLAGS) -pvc $<

# Remove intermediate files, but keep the PDF
clean:
	$(COMPILER) -c $(MAIN_TEX)

# Remove all generated files, including the PDF
distclean:
	$(COMPILER) -C $(MAIN_TEX)
