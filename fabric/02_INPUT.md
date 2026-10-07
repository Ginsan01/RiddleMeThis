# SECTION: INPUT

## Template

```
# INPUT:

INPUT:
```

## Notes
- This is intentionally minimal — just a header and a repeated "INPUT:" marker.
- It acts as the seam where Fabric appends whatever content is piped in via stdin, --file, -u (URL), or -y (YouTube transcript).
- Never add instructions after this marker; everything after it is treated as raw data, not directives.
- Some community patterns omit the duplicate line and use only "INPUT:" once — either form works, but the official template uses both a header and the marker line.
