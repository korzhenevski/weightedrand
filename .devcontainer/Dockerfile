FROM mrothy/go2go:latest
RUN apk add --no-cache \
    git \
    bash \
    zsh

RUN GO111MODULE=on go get -v \
    golang.org/x/tools/gopls@dev.go2go \
    golang.org/x/tools@dev.go2go

# https://github.com/golang/go/issues/39619
# Extensions > Install from VSIX...
#
# Bug with this, it shares ID with golang-nightly, so... autoupdate will break it.
# looks to be changing IDs soon, see https://github.com/golang/vscode-go/commit/38e85e57530285314f55eeaf0e243d5fa5222864
RUN cd /root && wget https://github.com/golang/vscode-go/releases/download/20200616/go-nightly-0.0.0.vsix
