#
# Copyright 2018 Dgraph Labs, Inc. and Contributors
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

PROTO_PATH := ${GOPATH}/src:.
PROTO_PATH := ${PROTO_PATH}:${GOPATH}/src/github.com/gogo/protobuf
PROTO_PATH := ${PROTO_PATH}:${GOPATH}/src/github.com/dgraph-io/dgo/protos

.PHONY: help
help:
	@echo Use \"make regenerate\" to proceed.

clean:
	@mkdir -p pb && rm -f pb/pb.pb.go

regenerate: clean
	@protoc \
		--proto_path=${PROTO_PATH} \
		--gofast_out=plugins=grpc,Mapi.proto=github.com/dgraph-io/dgo/protos/api:pb \
		pb.proto
	@echo Done.